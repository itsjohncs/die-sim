# Die Simulator

This is (fairly) simple program for rolling dice.

![Animation of program in use](https://raw.github.com/itsjohncs/die-sim/master/demo.gif)

It has grown in functionality _very_ slowly over time and I've only added additional functionality where I've been personally and repeatedly annoyed with the lack of it. For example, `!crit` was added because I usually enter my attack and damage rolls at the same time (ex: `d20+8, d8+5, 4d6`) which meant I had to pull out a calculator and double the damage dice myself whenever I crit (ie: once or twice a session on average).

## How to Run

```shell
git clone https://github.com/itsjohncs/die-sim.git
./die-sim/die.py
```

If you're on a mac like me, you'll want to consider using a different Python besides the system one. The system Python uses a shitty alternative to the `readline` library, so you don't get nearly as many prompt features (like the super useful reverse history search) while using the tool.
