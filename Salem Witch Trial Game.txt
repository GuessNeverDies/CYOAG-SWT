from graphics import *
import random

def intro():
    global win
    win = GraphWin("Salem Witch Trial", 800, 700)
    win.setBackground("white")
    onScreenText = Text(Point(win.getWidth() / 2, (win.getHeight() / 2)),
                        "The Salem Witch Trials were a series of court trials held in quick succession.\n" +
                        "\n" +
                        "They started from early 1692 and ended mid-1693. They were cases dealing with witchcraft.\n" +
                        "\n" +
                        "Witchcraft is usually regarded as striking a deal with the devil, serving it in exchange for loyalty.\n" +
                        "\n" +
                        "Salem Witchcraft cases often follow young children having seizure-like moments, spasming and acting unusual.\n" +
                        "\n" +
                        "They would then accuse a witch, and the witch would be put on trial. These trials were much\n" +
                        "\n" +
                        "different from what is normal in modern society.\n" +
                        "\n" +
                        "They often are seen as unfair when observed with modern bias. This, unfortunately, was not uncommon.\n" +
                        "\n" +
                        "Over time, convicted witches have been pardoned and officially excused, but the last 'witch' to be pardoned was\n" +
                        "\n" +
                        "Elizabeth Johnson Jr.\n" +
                        "\n" +
                        "Elizabeth was officially pardoned in 2022, 329 years after she was officially convicted.\n" +
                        "\n" +
                        "Elizabeth luckily was never executed, and lived to 1747, a respectable 77 years old.\n" +
                        "\n" +
                        "This game was originally developed following her story, but was branched off for gameplay purposes.\n" +
                        "\n" +
                        "I hope you enjoy!\n" +
                        "\n" +
                        "Oh, and press 'c' to continue for the rest of the game, unless you're making a decision.")
    onScreenText.setFill("blue")
    onScreenText.draw(win)
    reset("white", True)

def reset(color, keyInputTF):
    resetSquare = Polygon(Point(0, 0), Point(800, 0), Point(800, 700), Point(0, 700))
    resetSquare.setFill(color)
    resetSquare.setOutline(color)
    if not keyInputTF:
        resetSquare.draw(win)
    else:
        key = ''
        while key != 'c':
            key = win.getKey()
            if key == 'c':
                resetSquare.draw(win)

def decOne():
    key = ''
    while key != 'c' and key != 'p' and key != 'a':
        key = win.getKey()
        if key == 'c' or key == 'p' or key == 'a':
            return key

def decisionOne():
    onScreenText = Text(Point(win.getWidth() / 2, (win.getHeight() / 2) - 100),
                        "The year is 1692. You are just an ordinary citizen.\n" +
                        "You live in a town called Salem. A lot of weird things have happened recently.\n" +
                        "Something about witches? You can't remember.\n")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    salemMap = Image(Point(win.getWidth() / 2, (win.getHeight() / 2) + 150), 'SWT_MAP.png')
    salemMap.draw(win)
    reset("white", True)
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "Suddenly, you hear people outside your door.\n" +
                        "They're knocking really loudly, some of them are shouting.\n" +
                        "You walk over, and open the door. It's chaos.\n")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    reset("white", True)
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "People rush at you. They have torches and pitchforks.\n")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    riot = Image(Point(win.getWidth() / 2, (win.getHeight() / 2) + 200), 'SWT_RIOT.png')
    riot.draw(win)
    reset("white", True)
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "Suddenly, everything turns black.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    reset("black", True)
    reset("white", True)
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You wake up in a courtroom. You can't move.\n" +
                        "The judge is saying something about witches?\n")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    reset("white", True)
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "... in the case of ... we ... jury ... find defendant ... guilty\n" +
                        "... on account of witchery ... devil ...")
    onScreenText.setFill("red")
    onScreenText.draw(win)
    reset("white", True)
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You hear the sentence you must serve, loud and clear.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    reset("white", True)
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "Defendant shall be hung in three month's time.")
    onScreenText.setFill("red")
    onScreenText.draw(win)
    reset("white", True)
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "What do you do? Press 'c' to challenge the verdict, press 'p' to plead, or press 'a' to accept")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    return decOne()

def decOneResC():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You dare challenge OUR verdict?\n" +
                        "The AUDACITY.\n" +
                        "Quick, hang them now, before they use their witchery on us!")
    onScreenText.setFill("red")
    onScreenText.draw(win)
    reset("white", True)
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You get hung and die.\n" +
                        "You've reached the CHALLENGE verdict.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    challengeImage = Image(Point(win.getWidth() / 2, win.getHeight() / 3), 'SWT_3.png')
    challengeImage.draw(win)
    reset("white", True)

def decOneResP():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "Hah! The witch is trying to plead for forgiveness!\n" +
                        "Like we would forgive you! You made a deal to the devil!\n" +
                        "As you are loyal solely to the devil! We cannot trust you!\n")
    onScreenText.setFill("red")
    onScreenText.draw(win)
    reset("white", True)
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "They hang you three months later after locking you in prison.\n" +
                        "You've reached the PLEADING ending.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    pleadImage = Image(Point(win.getWidth() / 2, win.getHeight() / 3), 'SWT_1.png')
    pleadImage.draw(win)
    reset("white", True)

def decOneResA1():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You accept the guilty verdict and you get hung 3 months later.\n" +
                        "You've reached the PACIFIST ending.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    pacifistImage = Image(Point(win.getWidth() / 2, win.getHeight() / 3), 'SWT_8.png')
    pacifistImage.draw(win)
    reset("white", True)

def decOneResA2():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You accept the verdict for now, do you accuse any other witches?\n" +
                        "Press 'y' to blame other witches, press 'n' to not accuse any other witches.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    key = ''
    while key != 'y' and key != 'n':
        key = win.getKey()
        if key == 'y':
            reset('white', False)
            decisionTwoAccuse()
        if key == 'n':
            reset('white', False)
            decisionTwoNoAccuse()

def decisionTwoAccuse():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "Which of the following would you like to blame?\n" +
                        "Sarah Good (g)\n" +
                        "Sarah Osborne (o)\n" +
                        "Both (b)")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    key = ''
    while key != 'g' and key != 'o' and key != 'b':
        key = win.getKey()
        if key == 'g':
            reset("white", False)
            decisionThreeB1('Sarah Good')
        elif key == 'o':
            reset("white", False)
            decisionThreeB1('Sarah Osborne')
        elif key == 'b':
            reset("white", False)
            decisionThreeB2()

def decisionTwoNoAccuse():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You decide not to blame any other witches.\n" +
                        "The trial is now over. What do you do?\n" +
                        "Type 'r' to run away, type 's' to sit and do nothing, or type 'w' to use your witch powers.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    key = ''
    while key != 'r' and key != 's' and key != 'w':
        key = win.getKey()
        if key == 'r':
            reset("white", False)
            decisionThreeNBR()
        elif key == 's':
            reset("white", False)
            decisionThreeNBS()
        elif key == 'w':
            reset("white", False)
            decisionThreeNBW()

def decisionThreeB1(sarah):
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You blame " + sarah +
                        " and she is hung with you in three months.\n" +
                        "Congratulations, you are now responsible the the life of an innocent woman.\n" +
                        "You've reached the ACCUSER ending.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    accuserImage = Image(Point(win.getWidth() / 2, win.getHeight() / 3), 'SWT_7.png')
    accuserImage.draw(win)
    reset("white", True)

def decisionThreeB2():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You blame both Sarah Good and Sarah Osborne.\n" +
                        "They are both tried as well for witchcraft and both are found guilty.\n" +
                        "You all are hung three months later.\n" +
                        "You've reached the TITUBA ending.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    titubaImage = Image(Point(win.getWidth() / 2, (win.getHeight() / 3) - 5), 'SWT_5.png')
    titubaImage.draw(win)
    reset("white", True)
    win.close()

def decisionThreeNBR():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You try and run away that night.\n" +
                        "As you reach the outer skirts of Salem, you suddenly see someone.\n" +
                        "It's your neighbor.\n" +
                        "You don't know if he sees you.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    reset("white", True)
    caught = random.randint(1, 10)
    if caught == 10:
        onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                            "He notices and reports you.\n" +
                            "You were caught and hung.\n" +
                            "You've reached the RUNAWAY ending.")
        onScreenText.setFill("black")
        onScreenText.draw(win)
        runawayImage = Image(Point(win.getWidth() / 2, win.getHeight() / 3), 'SWT_6.png')
        runawayImage.draw(win)
        reset("white", True)
    else:
        onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                            "He doesn't notice you, and you successfully escape.\n" +
                            "You've reached the ESCAPEE ending.")
        onScreenText.setFill("black")
        onScreenText.draw(win)
        escapeeImage = Image(Point(win.getWidth() / 2, win.getHeight() / 3), 'SWT_2.png')
        escapeeImage.draw(win)
        reset("white", True)

def decisionThreeNBS():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You leave the courtroom for now, unsure what to do.\n" +
                        "You mull over the court decision for a few months, and finally come to a decision.\n" +
                        "But, before you can do anything...")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    reset("white", True)
    death = random.randint(1, 10)
    if death >= 2:
        onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                            "You realize that you've lost track of time, and your execution date has come around.\n" +
                            "You are hung in front of a crowd of 100 people.\n" +
                            "You've reached the LAZY ending.")
        onScreenText.setFill("black")
        onScreenText.draw(win)
        lazyImage = Image(Point(win.getWidth() / 2, win.getHeight() / 3), 'SWT_8.png')
        lazyImage.draw(win)
        reset("white", True)
    else:
        onScreenText = Text(Point(win.getWidth() / 2, (win.getHeight() / 2) + 50),
                            "The craze of the witch trials has died down.\n" +
                            "You are set free and live out the rest of your life void of witchcraft accusations.\n" +
                            "You've reached the LUCKY ending.")
        onScreenText.setFill("black")
        onScreenText.draw(win)
        luckyImage = Image(Point(win.getWidth() / 2, (win.getHeight() / 3) - 50), 'SWT_FLC.png')
        luckyImage.draw(win)
        reset("white", True)

def decisionThreeNBW():
    witchcraft = random.randint(1, 2)
    if witchcraft == 2:
        onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                            "You try and use your nonexistent witch powers.\n" +
                            "Nothing happens. What do you do now?\n")
        onScreenText.setFill("black")
        onScreenText.draw(win)
        reset("white", True)
        decisionFour()
    elif witchcraft == 1:
        onScreenText = Text(Point(win.getWidth() / 2, (win.getHeight() / 2) + 100),
                            "You try to use your witch powers, knowing that you don't have any.\n" +
                            "At first, people don't notice you. Once they do, though, they just watch and laugh.\n" +
                            "The judge and jury review the case, and decide to let you live.\n" +
                            "You live the rest of your life entertaining the public.\n" +
                            "You've reached the JESTER ending.")
        onScreenText.setFill("black")
        onScreenText.draw(win)
        jesterImage = Image(Point(win.getWidth() / 2, win.getHeight() / 3), 'SWT_CF.png')
        jesterImage.draw(win)
        reset("white", True)

def decisionFour():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "Nothing seems to really happen? What did you expect?\n" +
                        "What do you do now? Your execution is closing in so you don't have much time\n" +
                        "Press 'p' to pretend to be possessed, 'c' to confess to witchcraft, or 'f' to have a fit")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    key = ''
    while key != 'p' and key != 'c' and key != 'f':
        key = win.getKey()
        if key == 'p':
            reset("white", False)
            decFiveP()
        elif key == 'c':
            reset("white", False)
            decFiveC()
        elif key == 'f':
            reset("white", False)
            decFiveF()

def decFiveP():
    if random.randint(1, 5) == 1:
        decFiveP_A()
    else:
        decFiveP_B()

def decFiveP_A():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You pretend to be possessed, and someone sees you.\n" +
                        "You are immediately reported and hung.\n")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    reset("white", True)
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "Hang them now, before they spread it to us!")
    onScreenText.setFill("red")
    onScreenText.draw(win)
    reset("white", True)
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You've reached the ALMOST ending.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    almostImage = Image(Point(win.getWidth() / 2, (win.getHeight() / 2) + 100), 'SWT_8.png')
    almostImage.draw(win)
    reset("white", True)

def decFiveP_B():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "After pretending to be possessed, everyone gets scared of you.\n" +
                        "Instead of being hung, you are exiled from Salem.\n" +
                        "You leave Salem and settle in a nearby town called Marblehead.\n" +
                        "There, you start a new life and live the rest of your days as a free person.\n" +
                        "You've reached the FREE ending.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    reset("white", True)

def decFiveC():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You confess to everyone that you are a witch.\n" +
                        "No one pays you any attention as they are already convinced that you are a witch.\n" +
                        "What do you do now?\n" +
                        "Press 'a' to try and get everyone's attention, press or 'c' to try and convince everyone that you"
                        "are not a witch.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    key = ''
    while key != 'a' and key != 'c':
        key = win.getKey()
        if key == 'a':
            reset("white", False)
            decFiveOutcomeCA()
        if key == 'c':
            reset("white", False)
            decFiveOutcomeCC()

def decFiveOutcomeCA():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You try and get everyone's attention.\n" +
                        "People finally start to notice you.\n" +
                        "They hang you out of fear of witchcraft.\n" +
                        "You've reached the BACKFIRE ending.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    reset("white", True)

def decFiveOutcomeCC():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You run around telling everyone that you are a witch.\n" +
                        "They aren't amused, especially after the trial declared that you are a witch.\n" +
                        "You are hung in three months, after failing to cause any disruption.\n" +
                        "You've reached the IGNORED ending.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    reset("white", True)

def decFiveF():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You throw a fit, but no one seems to care.\n" +
                        "What do you do now?\n" +
                        "Press 'a' to try to get everyone's attention, or press 'v' to resort to violence.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    key = ''
    while key != 'a' and key != 'v':
        key = win.getKey()
        if key == 'a':
            if random.randint(1, 5) == 1:
                reset("white", False)
                decFiveOutcomeCA()
            else:
                reset("white", False)
                decFiveOutcomeFA()
        elif key == 'v':
            reset("white", False)
            decFiveOutcomeFV()

def decFiveOutcomeFA():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You try and get everyone's attention.\n" +
                        "After a good few attempts, it finally works.\n" +
                        "People see you having fits and remember the girls that accused you in the first place.\n" +
                        "You are called back into the court, and eventually, a trial is held to find the real witch.\n" +
                        "You are excused of all your charges, and live out the rest of your life.\n" +
                        "You've reached the ACTOR ending.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    reset("white", True)

def decFiveOutcomeFV():
    onScreenText = Text(Point(win.getWidth() / 2, win.getHeight() / 2),
                        "You resort to violence, injuring 5 people and killing 1 person.\n" +
                        "After being caught, you are tried for the assault and found guilty.\n" +
                        "The judge calls for you to be burnt at the stake immediately.\n" +
                        "You've reached the VIOLENT ending.")
    onScreenText.setFill("black")
    onScreenText.draw(win)
    reset("white", True)

def main():
    intro()
    resOne = decisionOne()
    reset("white", False)
    if resOne == 'c':
        decOneResC()
    if resOne == 'p':
        decOneResP()
    if resOne == 'a':
        if random.randint(1, 10) == 1:
            reset("white", False)
            decOneResA1()
        else:
            reset("white", False)
            decOneResA2()


if __name__ == "__main__":
    main()