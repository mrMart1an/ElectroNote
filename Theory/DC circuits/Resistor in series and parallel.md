For any given network of resistor, an equivalent resistance can be calculated as a combination of the series and parallel resistors in the network.

![[Resistance network.jpeg]]

## Resistor in series
When resistor are connected in series, the same current $\large I$ pass through each resistors. Using [[Resistance and Ohm's law#Ohm's law|Ohm's law]] we can find the voltage drop $\large V_n$ across each resistor $\large R_n$ as:
$$\Large V_n = R_n \cdot I$$
The total voltage drop across the series resistors network is then given by:
$$\Large V = R_1 \cdot I + \dots + R_n \cdot I$$
$$\Large V = I \cdot (R_1 + \dots + R_n)$$
From the last equation we can calculate the equivalent series resistance as:
$$\Large R = \dfrac{V}{I} = R_1 + \dots + R_n$$
The equivalent resistance is the sum of the resistance of the individual resistor in the network.
## Resistor in parallel

When resistor are connected in parallel, the voltage drop $\large V$ across the terminal of each resistor is identical. Using [[Resistance and Ohm's law#Ohm's law|Ohm's law]] we can find the current $\large I_n$ through each resistor $\large R_n$ as:
$$\Large I_n = \dfrac{V}{R_n}$$
The total current through the network can be calculated as:
$$\Large I = \dfrac{V}{R_1} + \dots + \dfrac{V}{R_n}$$
$$\Large I = V\cdot (\dfrac{1}{R_1} + \dots + \dfrac{1}{R_n})$$
From the last equation we can calculate the equivalent parallel resistance as:
$$\Large \dfrac{1}{R} = \dfrac{I}{V} = \dfrac{1}{R_1} + \dots + \dfrac{1}{R_n}$$
$$\Large R = \dfrac{1}{\dfrac{1}{R_1} + \dots + \dfrac{1}{R_n}}$$
The equivalent resistance is the inverse of the sum of the inverse of the resistance of each resistor in the network.
#### Two resistor in parallel
If the network is compose of only two resistor the previews formula can be simplified as follows:
$$\Large R = \dfrac{R_1 \cdot R_2}{(R_1 \cdot R_2) \cdot (\dfrac{1}{R_1} + \dfrac{1}{R_2})}$$
$$\Large R = \dfrac{R_1 \cdot R_2}{R_1 + R_2}$$
#### Identical resistor in parallel
If the resistor in the network all share the same resistance, the formula for the equivalent resistance can be simplified as follows:
$$\Large R_1 = \dots = R_n \hspace{5em} R = \dfrac{1}{\dfrac{N}{R_n}} = \dfrac{R_n}{N}$$
## Mixed resistor network
If a resistor network is composed of resistor connected both in series and in parallel, the equivalent resistance can be calculate by applying the previously exposed rules in succession.