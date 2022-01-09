# Crosswalk Traffic Light
![Screenshot 2022-01-09 114102](https://user-images.githubusercontent.com/57734498/148670198-ddc03ae7-7aaa-4c43-8ed2-b63ace723888.png)

```C
// ********************************************
//	Muhammad Hafiduddin
//	G64180017
//	
//	Crosswalk Traffic Light
//	warna defaultnya adalah hijau. 
//	ketika tombol ditekan, maka LED akan delay selama 3 detik,
//	lalu warna akan berubah kuning selama 3 detik. kemudian
//	warna berubah merah selama 10 detik. setelah 15 detik,
//	warna berubah lagi menjadi kuning selama 3 detik dan akhirnya
//	kembali lagi jadi hijau.
// **********************************************


const int buttonPin = 2;  // push button pin
const int red_pin = 13;    // red LED pin
const int green_pin = 8;	// green LED pin
const int blue_pin = 12;	// blue LED pin

const int shortDelay = 3000; // Delay for green and yellow state
const int redDelay = 10000;	 // Delay for red state

int buttonState;  // variables to hold the push button states


void setup()
{
  // Set up the pushbutton pins to be an input:
  pinMode(buttonPin, INPUT);

  // Set up the LED pin to be an output:
  pinMode(red_pin, OUTPUT);   
  pinMode(green_pin, OUTPUT);
  pinMode(blue_pin, OUTPUT);
}

void loop()
{
  digitalWrite(green_pin, HIGH);
  
  buttonState = digitalRead(buttonPin);
  
  // if button are pressed
  if(buttonState == LOW){
    
    delay(shortDelay);
    
    digitalWrite(red_pin, HIGH);
    digitalWrite(green_pin, HIGH);
    delay(shortDelay);
    
    digitalWrite(red_pin, HIGH);
    digitalWrite(green_pin, LOW);
    delay(redDelay);
    
    digitalWrite(red_pin, HIGH);
    digitalWrite(green_pin, HIGH);
    delay(shortDelay);
    
    digitalWrite(red_pin, LOW);
    digitalWrite(green_pin, HIGH);

  }
  else
  {
    digitalWrite(green_pin, HIGH);
  }
}
```
