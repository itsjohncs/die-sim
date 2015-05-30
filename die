#!/usr/bin/env python

import random, re, collections, readline

RollInfo = collections.namedtuple("RollInfo", "input,num_rolls,max_value,plus")

INPUT_RE = re.compile("([0-9]+)?d([0-9]+)(?:([+-][0-9]+))?")
def parse_input(user_input):
    split_raw = [i.strip() for i in user_input.split(",")]
    for i in split_raw:
        match = INPUT_RE.match(i)
        if match is None:
            yield i
            continue

        # Parse out the interesting values
        num_rolls, max_value, plus = match.groups()
        yield RollInfo(
            input=i,
            num_rolls=int(num_rolls or 1),
            max_value=int(max_value),
            plus=int(plus or 0))

def make_rolls(roll_info):
    for i in xrange(roll_info.num_rolls):
        yield random.choice(range(1, int(roll_info.max_value) + 1))

def main():
    while True:
        try:
            raw = raw_input("> ")
        except EOFError:
            return

        if raw.lower() == "help":
            print "Enter desired rolls in format XdY+Z"
            print "    Ex: 3d5, 5d6+9, 1d7-2, d9"
            continue
        elif raw.strip() == "":
            continue

        for roll_info in parse_input(raw):
            if isinstance(roll_info, basestring):
                print "{} - <error: invalid input, type help for info>".format(roll_info)
                continue

            rolls = list(make_rolls(roll_info))
            result = sum(rolls) + roll_info.plus
            print "{} - {} (rolls: {})".format(roll_info.input, result, rolls)

if __name__ == "__main__":
    try:
        main()
    except KeyboardInterrupt:
        pass

    print
