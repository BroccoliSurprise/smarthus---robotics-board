# Kitronik Robotics Board - husets hjerne

## Steg 1 @showdialog

På gulvet i smarthuset har vi installert et *Kitronik Robotics Board*, et utvidelseskort lar oss koble til 8 servomotorer samtidig. (*Pluss mye annet gøy*)

I tillegg får micro:biten strøm fra batteripakken i huset, så vi trenger ikke å ha en USB-ledning koblet til hele tiden.

![bilde av kontrollenheten](https://d14xnrffmhx4ml.cloudfront.net/1661205910/smarthus-instruks-5693-large-compact-robotics-board-microbit-800x.jpg)

## Steg 2132 @showdialog
**NB!**
Koblingsbrettet beskytter veldig godt mot kortslutninger, men det er fortsatt viktig å skru strømmen av før dere skal koble ting sammen.

I midten på gulvet finner dere strømbryteren til batteripakken, og øverst til høyre på brettet er det også en av/på-bryter.

Hvis brettet lyser grønt, betyr det at strømmen **IKKE** er skrudd av. Vær varsom.


## Steg 022323 @showdialog
Til venstre på kortet er det 24 pinner som stikker opp. Ser dere nøye etter, kan dere lese at det står 
**GND, V **og** SIG** øverst, og** SV1, SV2 ... SV8** på høyresiden.

![bilde av plugger](https://d14xnrffmhx4ml.cloudfront.net/1661361573/smarthus-veiledning-robotics-plugger.jpg)

## Steg ein til @showdialog
Servomotorer kobles til slik, med den brune ledningen i **GND** og den gule i **SIG**.

![bilde av servo koblet til brettet](https://d14xnrffmhx4ml.cloudfront.net/1661361705/smarthus-veiledning-robotics-servo.JPG)

## Safety first @showdialog

Som ekstra sikkerhet anbefales det å ha en "turn off all outputs" som nødstopp i starten av programmet, slik at reset-knappen kan brukes som nødstopp om noe går galt.
```blocks
Kitronik_Robotics_Board.allOff()
basic.pause(1000)
```

## Steg 1 robotics Yeah


Hvis dere ser til venstre, har vi lagt til en ny type blokker i menyen: Robotics.

I stedet for å bruke de vanlige røde servo-blokkene fra MakeCode, må vi bruke de grønne servoblokkene fra denne menyen hvis vi skal kunne styre de med brettet.  

Hent et par **Set Servo**-blokker og test hvor mye dere klarer å få til å bevege seg. 


## Steg slutt 
Godt jobbet, lykke til med byggingen!

```template
Kitronik_Robotics_Board.allOff()
basic.pause(1000)
```

```ghost
input.onButtonPressed(Button.A, function () {
    Kitronik_Robotics_Board.servoWrite(Kitronik_Robotics_Board.Servos.Servo1, 0)
    Kitronik_Robotics_Board.servoStop(Kitronik_Robotics_Board.Servos.Servo1)
})
```