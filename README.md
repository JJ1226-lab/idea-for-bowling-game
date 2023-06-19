import random

def roll_ball(pins):
    knocked_down = random.randint(0, pins)
    return knocked_down

def play_bowling():
    total_score = 0
    frame = 1

    while frame <= 10:
        print("\nFrame", frame)
        pins = 10
        roll = 1
        frame_score = 0

        while roll <= 2:
            knocked_down = roll_ball(pins)
            pins -= knocked_down
            frame_score += knocked_down
            print("Roll", roll, "- knocked down", knocked_down, "pin(s)")

            if roll == 1 and knocked_down == 10:
                print("Strike!")
                break

            if roll == 2 and frame_score == 10:
                print("Spare!")
                break

            roll += 1

        total_score += frame_score
        print("Frame", frame, "score:", frame_score)
        print("Total score:", total_score)

        frame += 1

    print("\nGame Over")
    print("Final score:", total_score)

play_bowling()
