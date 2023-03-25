import random

sum = int(input("Кол-во ваших денег: "))

while sum>0:

    bet = int(input("Ваша ставка: "))

    while bet>sum:
        print("Недостаточно денег, введите корректную ставку:")

        bet = int(input("Ваша ставка: "))

    random_number = random.randint(2, 12)

    user_number = int(input("Сколько выпадет на костях? (от 2-х до 12-ти) "))

    while user_number>12 or user_number<2:
        print("Некорректное число!")
        user_number = int(input("Сколько выпадет на костях? (от 2-х до 12-ти) "))

    if user_number == random_number:
        print(f"Вы угадали! Ваш выигрыш {bet * 10}!")
        sum+=bet*10
        print(f"Ваш остаток {sum}")

    else:
        print(f"Выпало {random_number}!")
        print(f"Вы не угадали.")
        sum-=bet
        print(f"Ваш остаток {sum}")

    if sum<=0:
        print("У вас не достаточно денег для игры. ")
        sum+= int(input("Сколько вы хотите добавить? " ))