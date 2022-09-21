import random

TOTAL_DICE = 5
DICE_FACES = 6


def roll_dice():

    """
    :return: a list containing five integers representing dice rolls between 1 and 6.
    """

    roll_list = []
    for i in range(TOTAL_DICE):
        roll_list.append(random.randint(1, 6))
    return roll_list


def scoring():
    """
    No parameters
    :return: scorelist with other list appended into it
    Description: sends specific variables to individual list that are sent to the scorelist to be added together
    """
    # Variables to keep track of all possible dice roll outcomes

    oneCount = 0
    twoCount = 0
    threeCount = 0
    fourCount = 0
    fiveCount = 0
    sixCount = 0
    smallStraightScore = 0
    largeStraightScore = 0
    fullHouseScore = 0
    yahtzeeScore = 0
    bonusScore = 0
    # boolean to check if the bonus has been scored
    hadBonus = False

    x = roll_dice()
    print(" ".join(map(str, x)))

    # for loop to count the amount of a certain number in the dice roll
    for i in x:
        if i == 1:
            oneCount += 1
        elif i == 2:
            twoCount += 1
        elif i == 3:
            threeCount += 1
        elif i == 4:
            fourCount += 1
        elif i == 5:
            fiveCount += 1
        elif i == 6:
            sixCount += 1

    # Boolean to check if the number has already been scored
    valid = False
    while not valid:
        num_count = (input("how would you like to count this dice roll? "))

        if num_count not in commands:
            valid = True

            if num_count == "":
                num_count = (input("how would you like to count this dice roll? "))
            if num_count == "count 1":
                if oneCount == 0:
                    print("Not in the dice roll")
                    num_count = (input("how would you like to count this dice roll? "))
                else:
                    # appends the count into a list it's own specified list then appends the sum of that list into the scorelist and bonus counter
                    oneSc.remove(0)
                    option(num_count)
                    oneS.append(oneCount)
                    oneSc.append(oneCount)
                    scoreList.append(sum(oneS))
                    bonusCounter.append(sum(oneS))
                    # the input is then added to a list of commands so that it can not be used again
                    commands.append(num_count)

            elif num_count == "count 2":
                if twoCount == 0:
                    print("Not in the dice roll")
                    num_count = (input("how would you like to count this dice roll? "))
                else:
                    twoSc.remove(0)
                    option(num_count)
                    twoS.append(twoCount * 2)
                    twoSc.append(twoCount * 2)
                    scoreList.append(sum(twoS))
                    bonusCounter.append(sum(twoS))
                    commands.append(num_count)

            elif num_count == "count 3":
                if threeCount == 0:
                    print("Not in the dice roll")
                    num_count = (input("how would you like to count this dice roll? "))
                else:
                    threeSc.remove(0)
                    option(num_count)
                    threeS.append(threeCount * 3)
                    threeSc.append(threeCount * 3)
                    scoreList.append(sum(threeS))
                    bonusCounter.append(sum(threeS))
                    commands.append(num_count)

            elif num_count == "count 4":
                if fourCount == 0:
                    print("Not in the dice roll")
                    num_count = (input("how would you like to count this dice roll? "))
                else:
                    fourSc.remove(0)
                    option(num_count)
                    fourS.append(fourCount * 4)
                    fourSc.append(fourCount * 4)
                    scoreList.append(sum(fourS))
                    bonusCounter.append(sum(fourS))
                    commands.append(num_count)

            elif num_count == "count 5":
                if fiveCount == 0:
                    print("Not in the dice roll")
                    num_count = (input("how would you like to count this dice roll? "))
                else:
                    fiveSc.remove(0)
                    option(num_count)
                    fiveS.append(fiveCount * 5)
                    fiveSc.append((fiveCount * 5))
                    scoreList.append(sum(fiveS))
                    bonusCounter.append(sum(fiveS))
                    commands.append(num_count)

            elif num_count == "count 6":
                if sixCount == 0:
                    print("Not in the dice roll")
                    num_count = (input("how would you like to count this dice roll? "))
                else:
                    sixSc.remove(0)
                    option(num_count)
                    sixS.append(sixCount * 6)
                    sixSc.append(sixCount * 6)
                    scoreList.append(sum(sixS))
                    bonusCounter.append(sum(sixS))
                    commands.append(num_count)

            elif num_count == "skip":
                print()

            elif num_count == "small straight":
                # if there are one of certain numbers in a sequence
                if oneCount >= 1 and twoCount >= 1 and threeCount >= 1 and fourCount >= 1 \
                        or twoCount >= 1 and threeCount >= 1 and fourCount >= 1 and fiveCount >= 1 \
                        or threeCount >= 1 and fourCount >= 1 and fiveCount >= 1 and sixCount >= 1:
                    smallStraightsc.remove(0)
                    option(num_count)
                    smallStraightScore += 30
                    smallStraights.append(smallStraightScore)
                    smallStraightsc.append(smallStraightScore)
                    scoreList.append(sum(smallStraights))
                    commands.append(num_count)

            elif num_count == "large straight":
                # checks if the dice roll has a certain sequence
                if oneCount >= 1 and twoCount >= 1 and threeCount >= 1 and fourCount >= 1 and fiveCount >= 1 \
                        or twoCount >= 1 and threeCount >= 1 and fourCount >= 1 and fiveCount >= 1 and sixCount >= 1:
                    largeStraightsc.remove(0)
                    option(num_count)
                    largeStraightScore += 40
                    largeStraights.append(largeStraightScore)
                    largeStraightsc.append(largeStraightScore)
                    scoreList.append(sum(largeStraights))
                    commands.append(num_count)

            # checks if a number appears 3 times in row
            elif num_count == "three of a kind" or num_count == "3 of a kind":
                if oneCount >= 3 or twoCount >= 3 or threeCount >= 3 or fourCount >= 3 or fiveCount >= 3 \
                        or sixCount >= 3:
                    threeOfaKindc.remove(0)
                    option(num_count)
                    threeOfaKind.append(sum(x))
                    threeOfaKindc.append(sum(x))
                    scoreList.append(sum(threeOfaKind))

                    commands.append(num_count)

            # checks if a number appears four times in row
            elif num_count == "four of a kind" or num_count == "4 of a kind":
                if oneCount >= 4 or twoCount >= 4 or threeCount >= 4 or fourCount >= 4 or fiveCount >= 4 \
                        or sixCount >= 4:
                    fourOfaKindc.remove(0)
                    option(num_count)
                    fourOfaKind.append(sum(x))
                    fourOfaKindc.append(sum(x))
                    scoreList.append(sum(fourOfaKind))
                    commands.append(num_count)

            elif num_count == "full house":
                if (
                        oneCount >= 3 and twoCount >= 2 or threeCount >= 2 or fourCount >= 2 or fiveCount >= 2 or sixCount >= 2) \
                        or (
                        twoCount >= 3 and oneCount >= 2 or threeCount >= 2 or fourCount >= 2 or fiveCount >= 2 or sixCount >= 2) or (
                        threeCount >= 3 and twoCount >= 2 or oneCount >= 2 or
                        fourCount >= 2 or fiveCount >= 2 or sixCount >= 2) or (fourCount >= 3 and twoCount >= 2 or
                                                                               threeCount >= 2 or oneCount >= 2 or fiveCount >= 2 or sixCount >= 2) or \
                        (
                                fiveCount >= 3 and twoCount >= 2 or threeCount >= 2 or fourCount >= 2 or oneCount >= 2 or sixCount >= 2) or \
                        (sixCount >= 3 and twoCount >= 2 or threeCount >= 2 or fourCount >= 2 or fiveCount >= 2 or
                         oneCount >= 2):
                    fullHousec.remove(0)
                    option(num_count)
                    fullHouseScore += 25
                    fullHouse.append(fullHouseScore)
                    fullHousec.append(fullHouseScore)
                    scoreList.append(sum(fullHouse))
                    commands.append(num_count)

            elif num_count == "chance":
                chanceSc.remove(0)
                option(num_count)
                chanceS.append(sum(x))
                chanceSc.append(sum(x))
                scoreList.append(sum(chanceS))
                commands.append(num_count)

            elif num_count == "yahtzee":

                if oneCount >= 5 or twoCount >= 5 or threeCount >= 5 or fourCount >= 5 or fiveCount >= 5 \
                        or sixCount >= 5:
                    del yahtzeeSc[0]
                    option(num_count)
                    yahtzeeScore += 50
                    yahtzeeS.append(yahtzeeScore)
                    yahtzeeCount.append(yahtzeeScore)
                    yahtzeeSc.append(sum(yahtzeeCount))
                    scoreList.append(sum(yahtzeeCount))

                    if 2 <= len(yahtzeeCount):
                        del yahtzeeSc[0]
                        yahtzeeScore = 100
                        yahtzeeS.append(yahtzeeScore)
                        yahtzeeCount.append(yahtzeeScore)
                        yahtzeeSc.append(sum(yahtzeeS))

            else:
                print("not valid")

            if sum(bonusCounter) >= 63:
                bonusScore = 35
                bonusS.append(bonusScore)
                scoreList.append(sum(bonusS))
                hadBonus = True

            if hadBonus:
                bonusScore -= 35

        else:
            print("already used command")

    return scoreList


def score_card():
    """
    No parameters
    :return: Scorecard with scores and category in it
    """
    print("    Scorecard")
    print("  1's ", " 2's ", " 3's ", " 4's ", " 5's ", " 6's ")
    print(" ", "".join(str(oneSc)) , "", "".join(str(twoSc)), " ", "".join(str(threeSc)),
          " ", "".join(str(fourSc)), " ", "".join(str(fiveSc)), " ", "".join(str( sixSc)))

    print("Three of a Kind", "Four of a Kind", "Full House", "Small Straight", "Large Straight", "Yahtzee", "Chance")

    print("      ", "".join(str(threeOfaKindc)), "        ", "".join(str(fourOfaKindc)), "        ",
          "".join(str(fullHousec)), "           ", "".join(str(smallStraightsc)),
          "        ", "".join(str(largeStraightsc)), "        ", "".join(str(yahtzeeSc)),
          "     ", "".join(str(chanceSc)), "  ")


def play_game(num_rounds):
    print("**** starting round", rcount, "****")


def option(num_count):
    print("accepted", num_count)


if __name__ == '__main__':
    rcount = 1

    totalScore = []
    commands = []
    oneSc = [0]
    twoSc = [0]
    threeSc = [0]
    fourSc = [0]
    fiveSc = [0]
    sixSc = [0]

    smallStraightsc = [0]
    largeStraightsc = [0]
    fullHousec = [0]
    threeOfaKindc = [0]
    fourOfaKindc = [0]
    chanceSc = [0]
    yahtzeeSc = [0]
    bonusCounter = []

    yahtzeeCount = []

    num_rounds = int(input('What is the number of rounds that you want to play? '))
    seed = int(input('Enter the seed or 0 to use a random seed: '))
    if seed:
        random.seed(seed)
    while rcount <= num_rounds:
        oneS = []
        twoS = []
        threeS = []
        fourS = []
        fiveS = []
        sixS = []

        smallStraights = []
        largeStraights = []
        fullHouse = []
        threeOfaKind = []
        fourOfaKind = []
        chanceS = []
        yahtzeeS = []
        bonusS = []
        scoreList = []
        play_game(num_rounds)

        y = scoring()
        score_card()
        totalScore.append(sum(y))
        print("score is", sum(totalScore))

        rcount += 1

