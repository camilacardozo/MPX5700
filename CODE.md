//# MPX5700
//Sensor de Pressão - Série MPX5700
// Este programa funciona para o sensor MPX5700AP, mas não funciona para o sensor MPX5700DP.

float VoutA;   
float pressao;
float Vs = 5.0;
float Vout;

void setup() {
Serial.begin(9600);
}
 
void loop(){
VoutA= analogRead(A1);   
Vout=((VoutA*Vs)/1023); 
pressao = (((Vout/Vs)-0.04)/0.0012858); //relação matemática fornecida pelo datasheet
Serial.print(pressao);
Serial.println("kPa");
delay(1000);
}
