---
layout: page
title: Lidar output
---

<span class="image right">
    <img style="width: 1000px; height: 550px;" src="{{ 'assets/images/animated.gif ' | absolute_url }}" alt=""/>
    Fig. 1: Point cloud, generated by Garmin Lidar Lite 3. As an example we scanned a human standing free in a room.
</span>

<p>Here we present an example how the Lidar data can be analysed in R with the <a  href="https://cran.r-projecft.org/web/packages/rgl/rgl.pdf">RGL package</a>. The following script shows an attempt to generate a 3-dimensional plot (Fig. 1) from the lidar measurements:</p>


    #import libs
    library("RColorBrewer")
    library("rgl")

    #read exportet csv
    a = read.csv("/.../output.csv", header = F)

    #to calc pwm signals to angles
    pwm2w = function(pwm){
        pwm = pwm/10
        w = 18 * (pwm-2.5)
        return(w)
    }
    #add to a
    a[,4:5] = pwm2w(a[,1:2])
    names(a) = c("pwm_x", "pwm_y", "dist_cm", "winkel_x", "winkel_y")

    #calc the xyz coordinates (kartesian) from angles and  
    #dist (polar koordinates)
    xyz = function(x_winkel, y_winkel, dist){
        deg2rad = function(winkel){
            return(winkel*pi/180)
        }
        xrichtung = deg2rad(x_winkel)
        yrichtung = deg2rad(y_winkel)
        x = dist * sin(xrichtung) *cos(yrichtung)
        y = dist * sin(xrichtung) *sin(yrichtung)
        z = dist * cos(xrichtung)
        return(data.frame(x,y,z))
    }

    #apply on data
    gg = xyz(a$winkel_x,   a$winkel_y, a$dist_cm/100)
    #create as many colors as entrys in a
    colfunc <- colorRampPalette(c("green", "red"))
    cols = colfunc(dim(a)[1])
    #3d plot teh points
    plot3d(gg$x, gg$y, gg$z, size = 25, col = cols)

    Angle1 <- 5
    Angle <- rep(Angle1 * pi / 180, 360/Angle1)
    sum(Angle*180/pi)

    #Animation.dir <- paste(getwd(), "/animation", sep="")
    #Animation.dir
    #[1] "/home/user/working.folder/animation"
    for (i in seq(Angle)) {
        view3d(userMatrix = rotate3d(par3d("userMatrix"),
                              Angle[i], 0, 1, 0))
        rgl.snapshot(filename=paste("Bilder/", sprintf("%03d", i),
        ".png", sep="")) 
    } 




<p class="copyright">&copy; Johannes Schnell. 13. September 2019 </p>