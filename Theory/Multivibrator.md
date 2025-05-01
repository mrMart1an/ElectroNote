A ***multivibrator*** is an electronic circuit used to implement a variety of simple two-state devices such as relaxation oscillators, timers, latches and flip-flops.
The multivibrator get it's name from it's harmonic rich output.

There are ***three*** types of multivibrator circuits:
1. ***Astable multivibrator***, in which the circuit isn't stable in either state and it continually switches from one state to the other. This circuit functions as a [[Relaxation oscillator]].
2. ***Monostable multivibrator***, in which one of the states is stable, but the other state is unstable and transient. A trigger pulse causes the circuit to switch to the unstable state and, after a set amount of time, the circuit will go back to the stable state. This circuit is useful for creating a pulse with a fixed duration in response to some external event.
3. ***BIstable multivibrator***, in which the circuit is stable in either state. It can be flipped from one state to the other by an external trigger pulse. This circuit is use to implement [[Theory/Flip-Flop|Flip-Flops]] and [[Theory/Latch|Latches]].

## Astable
An astable multivibrator consists of two amplifying stages connected in a positive feedback loop by two capacitive-resistive coupling networks. The amplifying elements may be junction or field-effect transistors, vacuum tubes or operational amplifiers.

The two output terminals can be defined at the active devices and have complementary states. One has high voltage while the other has low voltage, except during the brief transitions from one state to the other.
#### Operation
The circuit has two unstable states that change alternatively very quickly because of the positive feedback.

#### Sources
- https://en.wikipedia.org/wiki/Multivibrator