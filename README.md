# Arduino-RFID-Lock-System

![Screenshot (729)](https://user-images.githubusercontent.com/118633170/209387960-1c23e9e0-4954-4c1b-8d1e-708f21c77275.png)


If you have hard-time 3d printing stuff and other materials which i have provided in this project please refer the professionals for the help, [JLCPCB](https://jlcpcb.com/RNA) is one of the best company from shenzhen china they provide, PCB manufacturing, PCBA and 3D printing services to people in need, they provide good quality products in all sectors

[JLCPCB](https://jlcpcb.com/RNA)


Please use the following link to register an account in [JLCPCB](https://jlcpcb.com/RNA)

https://jlcpcb.com/RNA


Pcb Manufacturing

----------

2 layers

4 layers

6 layers

jlcpcb.com/RNA



PCBA Services

[JLCPCB](https://jlcpcb.com/RNA) have 350k+ Components In-stock. You don’t have to worry about parts sourcing, this helps you to save time and hassle, also keeps your costs down.

Moreover, you can pre-order parts and hold the inventory at [JLCPCB](https://jlcpcb.com/RNA), giving you peace-of-mind that you won't run into any last minute part shortages. jlcpcb.com/RNA


3d printing

-------------------

SLA -- MJF --SLM -- FDM -- & SLS. easy order and fast shipping makes [JLCPCB](https://jlcpcb.com/RNA) better companion among other manufactures try out [JLCPCB](https://jlcpcb.com/RNA) 3D Printing servies

[JLCPCB](https://jlcpcb.com/RNA) 3D Printing starts at $1 &Get $54 Coupons for new users

RFID stands for Radio Frequency IDentification and it’s a non-contact technology that’s broadly used in many industries for tasks such as personnel tracking, access control, supply chain management, books tracking in libraries, tollgate systems and so on.[/column]

![Screenshot (731)](https://user-images.githubusercontent.com/118633170/209388028-9db65fbc-afaf-4bd1-b34e-1a2afc31e357.png)


The RFID reader consist of a radio frequency module, a control unit and an antenna coil which generates high frequency electromagnetic field. On the other hand, the tag is usually a passive component, which consist of just an antenna and an electronic microchip, so when it gets near the electromagnetic field of the transceiver, due to induction, a voltage is generated in its antenna coil and this voltage serves as power for the microchip.

Now as the tag is powered it can extract the transmitted message from the reader, and for sending message back to the reader, it uses a technique called load manipulation. Switching on and off a load at the antenna of the tag will affect the power consumption of the reader’s antenna which can be measured as voltage drop. This changes in the voltage will be captured as ones and zeros and that’s the way the data is transferred from the tag to the reader.

There’s also another way of data transfer between the reader and the tag, called backscattered coupling. In this case, the tag uses part of the received power for generating another electromagnetic field which will be picked up by the reader’s antenna.

When power ON this door lock, the servo motor activates and pushes the door lock forward. Also displayed as “Welcome, put your card” on the LCD. Then when the RFID tag is moved closer to the RFID reader, it is scanned. In that case, it is displayed as “scanning” on the LCD. Then, if the RFID tag is correct, the servo motor is activated and the door lock is pulled back. The LCD shows “Door is Open”. When the RFID tag is moved closer to the RFID reader again, if it gets the correct tag, the servo motor will push the lock forward. Displays “Door is locked” on LCD. If a wrong RFID tag is used according to the program, it will be displayed as “Wrong card” on the LCD.

The fingerprint access control systems are preferred only for high security or personal security solutions, are highly personalized, and are costly. The PIN and RFID are cost-effective solutions applicable to public access systems like hotel rooms, classrooms, and offices. Of these two, RFID access control systems come with higher security and offer wider applications. For example, RFID solutions can be used simultaneously for access control as well as attendance in school/college classrooms.

In this project, we are designing an RFID door lock system and will explore how the locking mechanism can be built in different ways.

The read bytes of NUID are stored in a character array. This character array is compared to a predefined NUID using user-defined compareNUID() function. The function returns a boolean value used to determine access control. If the scanned NUID is matched with the programmed ID, a message granting access is displayed on the OLED screen. If the scanned NUID does not match the programmed ID, a message denying access is displayed on the OLED screen.

The door lock system consists of two critical circuits – the access control system and a locking mechanism. For the access control system here, an RFID is used. This door lock uses an RC522 RFID reader to read MIFARE and NTAG compatible RFID cards. Each lock passes access to only one RFID card, so all other cards are denied access. The system can also be programmed to provide additional access to a master card, which may be used instead of a lost card. The user interface is designed using an SSD1306 OLED display. Therefore, the complete access control system is designed by interfacing the RC522 RFID reader and SSD1306 OLED display with Arduino UNO.

![Screenshot (734)](https://user-images.githubusercontent.com/118633170/209388079-127c231e-11f1-4eb0-a950-4369f99a6169.png)
![Screenshot (735)](https://user-images.githubusercontent.com/118633170/209388104-df3e83a5-89fe-4e42-abfd-6b51462cf45f.png)



Next, constants are defined for circuit connections with the OLED display, and an object of the Adafruit_SSD1306 class is instantiated. The constants for circuit connections with RC522 are defined, and an object of the MFRC522 class is instantiated. A variable to store the MIFARE key is defined. A byte array ‘ nuidPICC[]’ is defined to store 4 bytes of RFID NUID. Variables are declared to store string representations of the NUID in decimal and hexadecimal formats. Similarly, a variable to store a string representation of the MIFARE key is defined. A bitmap is stored in PROGMEM for site loge, and an array is defined for the same.

In the setup() function, the baud rate for serial communication is set to 9600 bps. The OLED display is initialized by calling display.begin(SSD1306_SWITCHCAPVCC) method and display is flashed by calling display.display() method. The SPI protocol is initialized by calling SPI.begin() method. The RFID module initializes the PCD_Init() method on the RFID object. The MIFARE key bytes are set to FF and stored in an upper-case string representation. The MIFARE key is published on the Serial Monitor. The OLED display is cleared, and the site logo is flashed.

In the loop() function, some initial messages are first flashed on the screen. RFID card/key/tag is detected by calling PICC_IsNewCardPresent() method on the RFID object. Next, the card NUID/UID is read by calling the PICC_ReadCardSerial() method on the RFID object. The MIFARE card type is detected using the PICC_GetType(rfid.uid.sak) method and displayed on the Serial Monitor. Next, the individual bytes of the NUID are accessed using the rfid.uid.uidByte[] property. First, the bytes are serialized in decimal format and converted to a string object. The string containing a decimal representation of NUID is published on the Serial Monitor. Next, the bytes are serialized in hexadecimal format and converted to a string object. The string containing a hexadecimal representation of NUID is published on the serial monitor.

![Screenshot (737)](https://user-images.githubusercontent.com/118633170/209388143-b28fa69f-ecd9-4701-9367-d70f346e1dc8.png)
![Screenshot (738)](https://user-images.githubusercontent.com/118633170/209388171-bea4869e-fee1-466d-9317-18f6f04f7219.png)


The RC522 RFID reader is interfaced with Arduino using SPI protocol. The following circuit connections are made for interfacing the RFID reader with Arduino UNO. To learn more about reading RFID cards using RC522,

The locking mechanism can be built in two different ways. A do-it-yourself lock can be designed using a servo motor in one method. If the locking mechanism is built using a servo motor, it requires a PWM pin on Arduino for control.

It is recommended that servo is provided separate power supply using batteries as power fluctuations from the servo motor can damage the Arduino board.

In the second method, the lock can be designed using a solenoid lock. In this case, the lock can be controlled using any GPIO on Arduino via a relay module.

The RFID reader used to design this door lock is RC522. This RFID reader can read MIFARE and NTAG compatible RFID cards. The RFID cards either have a 7-byte long Unique Identity Number (UID) or 4-byte long Non-Unique Identity Number (NUID). Even if NUID cards are used, there is almost no possibility of getting two cards with the same NUID. The locking systems are designed such that the ID number of scanned cards is not disclosed in the process of access control. Even if the ID of a card is accessed from a different device, it is far from possible to get an RFID card of the same ID number.

When an RFID card is scanned through the RC522, it reads the NUID/UID of the particular card. The scanned NUID is compared against a pre-stored ID number for the door lock system. If the ID of the scanned card matches with the programmed ID, a welcome message is displayed on the OLED display. If the ID of the scanned card does not match with the programmed ID, the door remains unlocked, and a message denying access is displayed on the OLED display. At the same time, the door is unlocked either by rotating the servo in case of DIY servo lock or activating the relay in case of solenoid lock. The lock is programmed to pass access to only one RFID card.

![Screenshot (743)](https://user-images.githubusercontent.com/118633170/209388271-7747890f-3ce6-4a59-a789-f0ac9495fca8.png)
![Screenshot (744)](https://user-images.githubusercontent.com/118633170/209388282-a0bd8884-0876-4563-b54f-3633a596965c.png)


The code

The sketch begins with importing SPI and MFRC522 library for working with the RC522 reader. The library used in this project is Arduino MFRC522 Library from miguelbalboa, available at Github. Download the library as a ZIP file. Navigate to Sketch->Include Library->Add .ZIP Library in Arduino IDE. Select the rfid-master.ZIP, and the library for RC522 is added to the Arduino environment.

This is followed by importing Wire, Adafruit_GFX, and Adafruit_SSD1306 libraries for working with SSD1306 OLED. These libraries can be easily found in the library manager.
