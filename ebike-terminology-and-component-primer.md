## eBike Terminology & Component Primer

When discussing ebikes, you'll see these terms used frequently. I'm going to use some analogies here, but keep in mind that analogies are only useful for gaining an understanding. They are not hard-and-fast rules.

* **Volts (V).** In an electrical system, voltage could be thought of as "pressure"; similar to water pressure. Voltage is one component of power.
* **Amps (A).** Amps can be thought of as "volume"; similar to the volume of flow of water. Amperage is the other component of power.
* **Watts (W).** In physics terms, power is the rate of doing work. If you have more power, you can do more work, more quickly. It is literally `power = work/time`. Put another way, it is a measure of work done per unit of time. E.g., weight lifted a certain distance within 1 minute; a crank rotated a certain number of times in 1 hour; etc. You can compute watts by multiplying volts times amps. For example, 48V \* 25A = 1,200W. With some basic algebra, you can work backwards from any two components of the three to figure out the third.
* **Amp-hours (Ah).** This term is related to amps, but it is not exactly the same. Amp-hours are literally how long a certain flow of amperage is maintained. If you maintain 10A for 1 hour, that is equivalent to 10Ah. If you maintain 10A for 2 hours, that is 20Ah. This is a measure of amp capacity.
* **Watt-hours (Wh).** Similar to amp-hours, watt-hours tell you how long a level of power has been maintained. The math works the same, but with watts instead of amps. E.g., 250W for 1 hour is 250Wh; 250W for 2 hours is 500Wh.
* **Ohms (Ω).** This is the measure of resistance in an electrical circuit. This is the point where people start getting freaked out, but you really don't need to learn too much math here. You just need to know that resistance in a circuit causes the voltage to drop (or "sag"). All circuits have resistance, and in an ebike, both the battery and motor have resistance that will cause voltage to "sag" when under load. You'll hear more about this later.

The electricity in an ebike starts at the battery and powers the motor. The amount of power transmitted to the motor is regulated by the controller. So the flow looks like this:

`[BATTERY]<====>[CONTROLLER]<====>[MOTOR]`

In terms of specification, there are two main categories of capability: voltage and amperage.

**Voltage Compatibility**

All components in an ebike system must use a compatible voltage. This starts with the battery, since it is the source of voltage in an ebike system. From here, all components must be compatible:

* Controllers will specify their supported voltage. Some controllers can support a range of voltages, but they may require reconfiguration. This configuration can be a jumper inside the controller, a connection that must be soldered or cut, or a software change. You'll want to check with the controller vendor before making any assumptions.
* In the vast majority of cases, motors aren't really voltage specific. The exception are motors with integrated controllers (which I don't recommend). Insulation is what limits voltage capacity, but most motors you'll find can easily take common ebike battery voltages of 36, 48, and 52V. Many can be pushed up to 72V and beyond.
* Peripherals like the display must also be considered. Many displays can accept a range of voltages, just like controllers. Ditto for lighting. The same verification rules apply. Other peripherals like throttle and brake sensors are usually generic (can accept any common voltage).

The caveat here is when you move outside the typical ebike voltage range. As you move past 48V, you start to get into ranges that require more diligence. 52V is extremely common, but even that voltage level requires some double-checking. There are controllers that will shut down when connected to a fully charged 52V battery. The workaround is to discharge the battery slightly. You can avoid this by making sure your components can actually handle the voltage you intend to feed them.

**Amperage Capacity**

The other component of power is, of course, amperage. As you ride your bike at different speeds, amperage is the value that is (most commonly) varied. More load results in more amps being drawn through the electrical system. You'll need to make sure that your components can all handle the amp load required.

* The battery will have an amperage rating given as two parts: max and continuous. The max rating is a "burst" rating. It will usually be specified as something like "30A for 6 seconds". The time component is often omitted, but you should assume that it is short. The continuous rating is what the battery can output continuously under "standard conditions". That last bit is important. If it is exceptionally hot out (>85°F), you'll want to take it easy on your battery. More amps = more heat, and heat kills batteries. Your battery's max & continuous amp rating should *exceed* (be greater than) the controller rating. I like a little bit of a headroom. A minimum of 10% is good, but 15% - 20% is better. The more headroom you have, the less stressed your battery will be, the longer it will last.
* The BMS keeps track of the battery's state of charge (based on voltage), and will shut the battery down if it goes below a certain level. This is to protect the battery; lithium batteries can be permanently damaged by being discharged too far. The BMS will also shut the battery off it the voltage goes too high. Finally, it "balances" the voltage of individual cells within the battery. The BMS will be rated for a voltage and amperage. You should choose a BMS that matches your battery voltage exactly (it's based on the number of cells in series in your pack) and is capable of flowing your battery's max and continuous amperage on the "discharge" side.
* The controller is what regulates the amperage sent to the motor. Combined with the voltage, this is what determines the actual power output to the motor. So for example, if you combine a 52V battery with a 20A controller, you'll end up with 52V \* 20A = 1,040W sent to the motor.
* Motors are rated for input power. For example, a 1,500W motor is "rated" to accept 1,500W of input power at the manufacturer's specified duty cycle (time spent running versus idle). Motor power ratings are fuzzy (and that's putting it lightly). Plenty of people run Chinese 1,500W hub motors at 2,500W. The limit, as usual, is heat. Running a motor at greater than its rated input generates heat. Just remember that it is *your* responsibility to monitor your ebike's operation. If you buy a 1,500W motor, run 2,500W through it, you should put systems in place to monitor the motor temperature (i.e., a temperature sensor). By this point, you should be able to do the math to figure out the appropriate voltage and amperage for your desired power level.
