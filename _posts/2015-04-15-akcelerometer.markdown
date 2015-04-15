---
layout: post
title:  "Akcelerometer"
short-title:  "Akcelerometer"
date:   2015-04-15 23:24:00
categories: detekcia
---

Nazýva sa tiež senzor zrýchlenia. Meria akceleráciu vo všetkých troch smeroch
súradnicového systém, v ktorom je zahrnuté aj gravitačné zrýchlenie. To znamená, že
pokiaľ necháme zariadenie v pokoji položené na stole, zrýchlenie v jednej z osí bude rovné
gravitačnému zrýchleniu.

Akcelerometer nám poskytuje tri číselné údaje predstavujúce zrýchlenie v smere osí X, Y
a Z pri každej zmene v pohybe zariadenia. Akcelerácia, alebo zrýchlenie je miera zmeny
rýchlosti objektu v čase.

Akcelerometer patrí medzi senzory s okamžitou odozvou. To znamená, že pokiaľ
zariadenie mení svoju polohu, senzor nám poskytuje dáta tak často, ako to dovoľuje
samotný čas vykonávania metódy na ich zachytenie.

Takmer každé mobilné zariadenie tento senzor má. Je to veľmi používaný senzor, pretože
využíva asi 10-krát menej batérie, než ostatné pohybové senzory.

K dátam z akcelerometra vieme jednoducho pristúpiť pomocou rozhrania *SensorEventListener*.
Nasledujúcim kódom spustíme *listener*, ktorý nám v metóde *onSensorChanged* poskytuje dáta z akcelerometra:

{% highlight java %}
sensorManager = (SensorManager) c.getSystemService(c.SENSOR_SERVICE);
sensorManager.getDefaultSensor(Sensor.TYPE_ACCELEROMETER);
accelerometer = sensorManager.getDefaultSensor(Sensor.TYPE_ACCELEROMETER);
sensorManager.registerListener(this, accelerometer, SensorManager.SENSOR_DELAY_NORMAL);
{% endhighlight %}

V metóde *onSensorChanged* potom vieme pristúpiť k dátam z akcelerometra nasledovne:

{% highlight java %}
public void onSensorChanged(SensorEvent event) {

    float x = event.values[0];
    float y = event.values[1];
    float z = event.values[2];

}
{% endhighlight %}