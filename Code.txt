
#define sensor_pin D6 
unsigned long start_time = 0;
unsigned long end_time = 0; 
int steps =0; 
float step_old=0;
float temp 0; 
float rpm=0;

void setup(){
 Serial.begin(9600);
 pinMode(sensor_pin, INPUT_PULLUP);
}
void loop(){ 
 start_time=millis();
 end_time=start_time+1000; 
 while(millis()<end_time)
 {
 if(digitalRead(sensor_pin))
 {
 steps = steps + 1;
 while(digitalRead(sensor_pin));
 }
 }
 temp = steps - step_old;
 step_old = steps;
 rpm = ((temp*60)/16);
 Serial.print("RPM = ");
 Serial.println(rpm,DEC);
