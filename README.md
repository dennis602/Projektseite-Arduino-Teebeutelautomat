# Arduino-Teebeutelautomat
## Informatik-Projekt von Peter und Dennis, 12ab

##Inhaltsverzeichnis

[Vorwort](1)

### <a name="1"></a>Vorwort

Im unserem ersten Projekt hatten wir sehr gute Erfahrungen Mit Arduino gemacht. Deshalb wollten wir disesmal auch gerne wieder mit dieser Soft- und Hardware arbeiten. Da unser Parkhaus aber nicht genug Potential bot, mussten wir uns etwas neues ausdenken, um den Anforderungen für dieses Halbjahr grerecht zu werden. Denn jetzt sollten wir vom Programmieren her anspruchsvoller und versierter werden. Da es mit Arduino aber noch zahlreiche weitere und auch durchaus anspruchsvollere Möglichkeiten gibt, entschieden wir uns schlussendlich dafür, beim Arduino zu bleiben. Dann haben wir erstmal, ohne uns groß Gedanken über unser Projekt zu machen, rumprobiert und sind schließlich an fogenden neuen  Elementen hängengeblieben: Taster, Stepper-Motor, Motor-Shield, Mega-Arduino und einem Summer/Pieper. Daraus wollten wir dann eine Teebeutelmaschine machen. Eine Tasse wird auf einen Platz gestellt und sobald dies ein Ultraschallsensor erkennt und ein Taster für einen zur Wahl stehenden Modus gedrückt wird. Dann fährt ein bestimmts Programm ab. Zuerst wird ein Teebeutel in die Tasse getunkt, während der Zieh-Zeit wird er einige Male hoch und runterbewegt, sobald er fertig ist, ertönt ein Signalton und zum Schluss fährt eine Konstruktion über die Tasse, auf die dann der Beutel fallen kann. Wir konnten unser großes Projekt also wieder aus mehreren kleineren Aufbauen, was ja auch letztes Mal schon das Prinzip unserer Arbeit war.


## Das Motorshield

Um einen Motor präzise steuern zu können, haben wir uns mit dem sogenannten Arduino Motorshield beschäftigt. Dieses ist ein weiteres Board, welches man auf den Mikrocontroller aufstecken kann. 

![Motorshield](https://github.com/dennis602/Projektseite-Arduino-Teebeutelautomat/blob/master/Motorshield%20Demobild.jpg?raw=true)

Da wir aber weiterhin die Ports des Mikrokontrollers nutzen wollten, haben wir nur die nötigen Ports per Kabel mit dem Motorshield verbunden. 

Das Motorshield besitzt mehrere Anschlüsse für DC-Motoren (Gleichstrommotoren), Steppermotoren (Schrittmotoren, s. ...) und Servos. Man kann eine externe Stromquelle zwischen 5 und 12 Volt anschließen, um den Mikrocontroller zu entlasten.

Um das Motorshield im Sketch einzubauen, muss man vorher die entsprechende Bibliothek aus dem Internet herunterladen und sie per "#include <AFMotor.h>" einbinden. Von nun an gibt es feste Befehle, mit denen man den Motor sehr genau und präzise steuern kann. 

![Sketch Motorshield](https://github.com/dennis602/Projektseite-Arduino-Teebeutelautomat/blob/master/includeAFMotor.PNG?raw=true)



## Der Steppermotor

Der Steppermotor ist eine Art der Elektromotoren. Es handelt sich um einen Synchronmotor, der durch mehrere innere Spulen ein rotierendes Magnetfeld erzeugt und so eine Umdrehung in 2048 sehr feine Schritte aufteilen kann. Er entwickelt zwar eine relativ langsame Drehgeschwindigkeit, dafür aber ein hohes Drehmoment. 

Durch die Aufteilung in 2048 Schritte ist die Steuerung sehr exakt. Im Sktech führt man ihn mit "AF_Stepper" ein, legt im Void Setup per "motor.setSpeed()" eine Geschwindgkeit fest und kann im Void Loop durch "motor.step()" festlegen, wie viele der 2048 Schritte er machen soll und, ob er vorwärts oder rückwärts drehen soll.

![Sketch Stepper](https://github.com/dennis602/Stundenprotokoll-II/raw/master/Code_motorshield_1.PNG?raw=true)

Damit ist er für unser Projekt bestens geeignet.



Quellen

https://www.generationrobots.com/de/401113-arduino-motor-shield-rev-3.html

https://funduino.de/nr-15-schrittmotor
