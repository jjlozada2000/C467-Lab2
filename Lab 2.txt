import re

file = open("ingest_this.txt", "r")

text_line = 1

for line in file:
    numbers = re.findall(r'\d+', line)

    print("Line", text_line)

    if len(numbers) == 0:
        print(" no numbers found")
    else:
        checked = []

        for num in numbers:
            if num not in checked:
                count = numbers.count(num)
                print(" ", num, "-", count, "time(s)")
                checked.append(num)
    
    text_line = text_line + 1

file.close()

"""

ian@Julians-MacBook-Pro-7 Lab 2 % python3 main.py
Line  1
  67 - 2 time(s)
Line  2
  67 - 1 time(s)
Line  3
  67 - 3 time(s)
Line  4
  67 - 3 time(s)
Line  5
 no numbers found

"""