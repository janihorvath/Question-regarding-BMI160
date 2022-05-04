# Question-regarding-BMI160
Please answer my question

Dear Friend!

My name is János from Hungary. I'm using your library: MH-BMI160 for my Arduino project, thank you for creating it!

I wrote a simple sketch which makes 2000 gyro and accelerometer measurements, calculates the average measuring time, and then prints it.
The value I get is consistent 24ms/measurement.

I wanted to boost this value a little bit for drone project and decided to edit the parameters in your library to change output data rate.
In the MH_BMI160.cpp file I edited two parameters: BMI160_ACCEL_ODR*; and BMI160_GYRO_ODR_*.

Snippet can be found here:

////////////////////////////////////////////////////////////////////////////////////////////////
void MH_BMI160::defaultParamSettg(struct bmi160Dev *dev)
{
  /* Initializing accel and gyro params with
  * default values */
  dev->accelCfg.bw = BMI160_ACCEL_BW_NORMAL_AVG4;
  dev->accelCfg.odr = BMI160_ACCEL_ODR_1600HZ;             <<<<<<Changed this one
  dev->accelCfg.power = BMI160_ACCEL_SUSPEND_MODE;
  dev->accelCfg.range = BMI160_ACCEL_RANGE_2G;
  dev->gyroCfg.bw = BMI160_GYRO_BW_NORMAL_MODE;
  dev->gyroCfg.odr = BMI160_GYRO_ODR_1600HZ;               <<<<<<<And this one
  dev->gyroCfg.power = BMI160_GYRO_SUSPEND_MODE;
  dev->gyroCfg.range = BMI160_GYRO_RANGE_2000_DPS;

  /* To maintain the previous state of accel configuration */
  dev->prevAccelCfg = dev->accelCfg;
  /* To maintain the previous state of gyro configuration */
  dev->prevGyroCfg = dev->gyroCfg;
}
  
////////////////////////////////////////////////////////////////////////////////////////////////
  
After uploading the sketch, the result remains exactly the same even if the rate is changed to the extremes: 25Hz to 3200Hz!
May you please help where and how to modify your library in order to get higher rates?
  
You can contact me via: janos.horvath.me@gmail.com
  
Thank you very much!
Best regards,
  János
