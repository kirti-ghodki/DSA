Question 1 →

Armstrong Numbers →

For a given 3 digit number, find whether it is Armstrong number or not. An Armstrong number of three digits is an integer such that the sum of the cubes of its digits is equal to the number itself. Return “Yes” if it is a Armstrong number else return “No”.
NOTE: 371 is an Armstrong number since 33 + 73 + 13 = 371


def is_armstrong_number(number):
    if not isinstance(number, int) or number < 100 or number > 999:
        return "No"

    digit1 = number % 10
    digit2 = (number // 10) % 10
    digit3 = number // 100

    sum_of_cubes = digit1 ** 3 + digit2 ** 3 + digit3 ** 3

    if sum_of_cubes == number:
        return "Yes"
    else:
        return "No"
