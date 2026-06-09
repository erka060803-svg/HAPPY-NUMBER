# HAPPY-NUMBER
def next_number(n):
    total = 0
    while n > 0:
        digit = n % 10
        total += digit ** digit
        n //= 10
    return total

def is_happy(n):
    seen = set()
    while n != 1 and n not in seen:
        seen.add(n)
        n = next_number(n)

    return n == 1

t = int(input())

for case in range(1, t + 1):
    n = int(input())
    
    if is_happy(n):
        print(f"Case #{case}: {n} is a Happy number.")
    else:
        print(f"Case #{case}: {n} is an Unhappy number.")

