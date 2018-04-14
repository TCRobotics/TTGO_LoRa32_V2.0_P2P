# TTGO_LoRa32_V2.0_P2P

LoRa Duplex communication based on Tom Igoe example of Arduino LoRa library customized for TTGO LoRa32 V2.0 Oled Board

Sends a message every 2 or 3 second, and get incoming messages. 
Implements a one-byte addressing scheme, with broadcast address.

Note: while sending, LoRa radio is not listening for incoming messages.

# Configuration
In one device keep only CONFIG 1 section uncommented and in the other device keep only CONFIG 2 uncommented (or modify it as you want;)
```C
//////////////////////CONFIG 1///////////////////////////
byte localAddress = 8;     // address of this device
byte destination = 18;     // destination to send to
int interval = 3000;       // interval between sends
String message = "Hi!";    // send a message
///////////////////////////////////////////////////////

/*
//////////////////////CONFIG 2///////////////////////////
byte localAddress = 18;    // address of this device
byte destination = 8;      // destination to send to
int interval = 2000;       // interval between sends
String message = "Hello!"; // send a message
///////////////////////////////////////////////////////
*/
```
# Pinout
```C
#define SX1278_SCK  5    // GPIO5  -- SX1278's SCK
#define SX1278_MISO 19   // GPIO19 -- SX1278's MISO
#define SX1278_MOSI 27   // GPIO27 -- SX1278's MOSI
#define SX1278_CS   18   // GPIO18 -- SX1278's CS
#define SX1278_RST  14   // GPIO14 -- SX1278's RESET
#define SX1278_DI0  26   // GPIO26 -- SX1278's IRQ(Interrupt Request)

#define OLED_SDA    21    // GPIO21  -- OLED'S SDA
#define OLED_SCL    22    // GPIO22  -- OLED's SCL Shared with onboard LED! :(
#define OLED_RST    16    // GPIO16  -- OLED's VCC?
```
# Frequency band selection
```C
#define LORA_BAND   868E6 // LoRa Band (Europe)
```

# Needed Libraries
- LoRa: https://github.com/sandeepmistry/arduino-LoRa

- ESP8266 OLED SSD1306: https://github.com/ThingPulse/esp8266-oled-ssd1306
