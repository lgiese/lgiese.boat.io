---
layout: page
title: Maximus Erat
---

<div class="row 200%">
	<div class="6u 12u$(medium)">
        <div class="table-wrapper">
				<table class="alt">
					<thead>
						<tr>
							<th>Cable connection</th>
							<th>GPIO set-up (Fig.2)</th>
              <th>GPIO set-up (Fig.2)</th>
              <th>Cable connection</th>
						</tr>
					</thead>
					<tbody>
                        <tr>
							<td>3V Temperature</td>
							<td>3V</td>
                            <td>5V</td>
                            <td>   </td>
						</tr>
						<tr>
							<td>Lidar blue <--> blue </td>
							<td>SDA GPIO2</td>
							<td>5V</td>
                            <td></td>
						</tr>
						<tr>
							<td>Lidar green <--> green </td>
							<td>SCL GPIO3</td>
							<td>GND</td>
                            <td>GND black</td>
						</tr>
						<tr>
							<td>Temperature Sensor green</td>
							<td>GPIO4</td>
							<td>GPIO14 (TXD)</td>
                            <td>   </td>
						</tr>
						<tr>
							<td>   </td>
							<td>GND</td>
                            <td>GPIO15</td>
							<td>   </td>
						</tr>
						<tr>
							<td></td>
							<td>GPIO17</td>
							<td>GPIO18</td>
                            <td>   </td>
						</tr>
                        <tr>
                            <td>   </td>
							<td>GPIO27</td>
                            <td>GND</td>
							<td>   </td>
                        </tr>
                        <tr>
                            <td>   </td>
							<td>GPIO22</td>
                            <td>GPIO23</td>
							<td>yellow --> Servo 1</td>
                        </tr>
                        <tr>
                            <td>   </td>
							<td>3V</td>
                            <td>GPIO24</td>
							<td>green --> Servo 2</td>
                        </tr>
					</tbody>
                    <tfoot>
                        <td colspan="4">Tab 1: Scatch of GPIO setting</td>
					</tfoot>
					<tfoot>
                        <td colspan="4">...</td>
                    </tfoot>
				</table>     
    </div>
    <span class="image fit">
            <img src="" alt="" /></span>
            <p> Fig 1: Foto of plumbed Raspi </p>
</div>
    <div class="6u$ 12u$(medium)">
        <span class="image fit">
            <img src="assets/images/RaspberryPiGPIOBelegung-789x1024.png" alt="" /></span>
            <p> Fig 2: Set-up Raspberry Pi 3 of <a href="https://indibit.de/raspberry-pi-die-gpio-schnittstelle-grundlagenbelegung/">https://indibit.de/raspberry-pi-die-gpio-schnittstelle-grundlagenbelegung/</a></p>
</div>
