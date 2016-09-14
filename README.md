网站地址：
	

-[1.cartoon](https://laixiao.github.io/game-engine/egret/cartoon/index.html)

-[2.legend](https://laixiao.github.io/game-engine/egret/legend2/index.html)

-[3.maggots](https://laixiao.github.io/game-engine/egret/maggots/index.html)


	-[feidegenggao](https://laixiao.github.io/Website/web/feidegenggao)
	
	-[muditaowang](https://laixiao.github.io/Website/web/muditaowang)
	
	-[wujindeheliu](https://laixiao.github.io/Website/web/wujindeheliu)
	






























<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
</head>
<body onload="setTimeout(WRIST_UPTest,10000);">

	<script>

	
/* 
		======传感器的使用======
		
		//0.在清单文件中添加相应特性
		Sensor								Capability
		
		Light sensor						http://tizen.org/feature/sensor.photometer
		Magnetic sensor						http://tizen.org/feature/sensor.magnetometer
		Pressure sensor						http://tizen.org/feature/sensor.barometer
		Proximity sensor					http://tizen.org/feature/sensor.proximity
		Ultraviolet sensor					http://tizen.org/feature/sensor.ultraviolet
		Heart rate monitor sensor			http://tizen.org/feature/sensor.heart_rate_monitor
		
		//1.查询可用的传感器：laixiao Available sensor: LIGHT,PRESSURE,HRM_RAW,GRAVITY,GYROSCOPE 
		var sensors = tizen.sensorservice.getAvailableSensors();
		console.log("laixiao Available sensor: " + sensors.toString()); 

		//2.不使用传感器
		setTimeout(function(){
			//4.取消传感器监听
			lightSensor.unsetChangeListener();
			//4.停止传感器
			lightSensor.stop();

		},1000*60*5);
		
*/


		
/* 
		//==========光线传感器Light==========
		
		var useLightSensor = function(){
			//1.检测设备是否支持此传感器
			var lightCapability = tizen.systeminfo.getCapability("http://tizen.org/feature/sensor.photometer");
			if (lightCapability === true){
			   	//2.获取Sensor对象 
			  	var lightSensor = tizen.sensorservice.getDefaultSensor("LIGHT");//对应的，比如光线：LIGHT	
				//3.设置监听：传感器数据改变时调用。
			  	lightSensor.setChangeListener(function(sensorData){
			  		console.log("3.setChangeListener : " + JSON.stringify(sensorData));
				});
			 	//4.启用传感器
				lightSensor.start(function(){
				   	lightSensor.getLightSensorData(
					   	function(sensorData){
					   		console.log("3.success： "+ JSON.stringify(sensorData));		     		
					   	}, 
					   	function(error){
					   		console.log("3.error： "+error);		   	
						}
				   	);
				});
			}	
		}
		
 */
/* 
		//==========压力传感器PRESSURE==========
		
		var usePressureSensor = function(){
			//1.检测设备是否支持此传感器
			var barometerCapability = tizen.systeminfo.getCapability("http://tizen.org/feature/sensor.barometer");
			if (barometerCapability === true){
			   	//2.获取Sensor对象 
			  	var pressureSensor = tizen.sensorservice.getDefaultSensor("PRESSURE");//对应的，比如光线：LIGHT	
				//3.设置监听：传感器数据改变时调用。
			  	pressureSensor.setChangeListener(function(sensorData){
			  		console.log("3.setChangeListener : " + JSON.stringify(sensorData));
				});
			 	//4.启用传感器
				pressureSensor.start(function(){
				   	pressureSensor.getPressureSensorData(
					   	function(sensorData){
					   		console.log("3.success： "+ JSON.stringify(sensorData));		     		
					   	}, 
					   	function(error){
					   		console.log("3.error： "+error);		   	
						}
				   	);
				});
			}	
		}
		
 */
/* 		
		//==========心率传感器HRM_RAW==========
		
		//添加权限：Privilege: http://tizen.org/privilege/healthinfo
		var useHRM_RAWSensor = function(){
			//1.检测设备是否支持此传感器
			var HRM_RAWCapability = tizen.systeminfo.getCapability("http://tizen.org/feature/sensor.heart_rate_monitor");
			if (HRM_RAWCapability === true){
			   	//2.获取Sensor对象 
			  	var HRM_RAWSensor = tizen.sensorservice.getDefaultSensor("HRM_RAW");//对应的，比如光线：LIGHT	
				//3.设置监听：传感器数据改变时调用。
			  	HRM_RAWSensor.setChangeListener(function(sensorData){
			  		console.log("3.setChangeListener : " + JSON.stringify(sensorData));
				});
			 	//4.启用传感器
				HRM_RAWSensor.start(function(){
					HRM_RAWSensor.getHRMRawSensorData(
					   	function(sensorData){
					   		console.log("3.success： "+ JSON.stringify(sensorData));		     		
					   	}, 
					   	function(error){
					   		console.log("3.error： "+error);		   	
						}
				   	);
				});
			}	
		}
		
 */
/* 
		//==========重力传感器GRAVITY==========
		
		//可画坐标系观察，放置于水平桌面上：y轴向上.
		var useGravitySensor = function(){
			//1.检测设备是否支持此传感器
			//var magnetometerCapability = tizen.systeminfo.getCapability("http://tizen.org/feature/sensor.magnetometer");
			//if (magnetometerCapability === true){
			   	//2.获取Sensor对象 
			  	var GravitySensor = tizen.sensorservice.getDefaultSensor("GRAVITY");//对应的，比如光线：LIGHT	
				//3.设置监听：传感器数据改变时调用。
			  	GravitySensor.setChangeListener(function(sensorData){
			  		console.log("3.setChangeListener : " + JSON.stringify(sensorData));
				});
			 	//4.启用传感器
				GravitySensor.start(function(){
					GravitySensor.getGravitySensorData(
					   	function(sensorData){
					   		console.log("3.success： "+ JSON.stringify(sensorData));		     		
					   	}, 
					   	function(error){
					   		console.log("3.error： "+error);		   	
						}
				   	);
				});
			//}else{
			//	console.log("=========not support=========");
			//}				
		}
		
	 */
/* 
		//==========陀螺仪GYROSCOPE==========
		
		var useGyroscopeSensor = function(){
			//1.检测设备是否支持此传感器
			//var magnetometerCapability = tizen.systeminfo.getCapability("http://tizen.org/feature/sensor.magnetometer");
			//if (magnetometerCapability === true){
			   	//2.获取Sensor对象 
			  	var GyroscopeSensor = tizen.sensorservice.getDefaultSensor("GYROSCOPE");//对应的，比如光线：LIGHT	
				//3.设置监听：传感器数据改变时调用。
			  	GyroscopeSensor.setChangeListener(function(sensorData){
			  		console.log("3.setChangeListener : " + JSON.stringify(sensorData));
				});
			 	//4.启用传感器
				GyroscopeSensor.start(function(){
					GyroscopeSensor.getGyroscopeSensorData(
					   	function(sensorData){
					   		console.log("3.success： "+ JSON.stringify(sensorData));		     		
					   	}, 
					   	function(error){
					   		console.log("3.error： "+error);		   	
						}
				   	);
				});
			//}else{
			//	console.log("=========not support=========");
			//}				
		}	
		
 */


/*  
//======================Human Activity Monitor==========================
	权限：<tizen:privilege name="http://tizen.org/privilege/healthinfo"/>

	 Monitor									Capability
	 
	 Pedometer and accumulative pedometer		http://tizen.org/feature/sensor.pedometer
	 Wrist up									http://tizen.org/feature/sensor.wrist_up
	 Heart rate monitor							http://tizen.org/feature/sensor.heart_rate_monitor
	 GPS										http://tizen.org/feature/location.batch


	 
 */


/*   
	 	//心率监听HRM
		
		var HRMTest = function(){
			//1.开始监测：HRM、WRIST_UP
			tizen.humanactivitymonitor.start("HRM", function(hrmInfo){
				//console.log("Heart Rate: " + hrmInfo.heartRate + "Peak-to-peak interval: " + hrmInfo.rRInterval + " milliseconds");
			   	console.log("==="+JSON.stringify(hrmInfo));  	
			}); 
			//停止监测
			//tizen.humanactivitymonitor.stop("HRM"); 
		}
		
*/

/* 
		//计步器
		
		var PedometerTest = function(){
			tizen.humanactivitymonitor.setAccumulativePedometerListener(function(pedometerInfo){
				//console.log("Step status : " + pedometerInfo.stepStatus);
			   	//console.log("Speed : " + pedometerInfo.speed);
			   	//console.log("Walking frequency : " + pedometerInfo.walkingFrequency);
			   	console.log(JSON.stringify(pedometerInfo));
			   	//tizen.humanactivitymonitor.unsetAccumulativePedometerListener();
			});
		}
		
 */
	
	</script>
</body>
</html>
