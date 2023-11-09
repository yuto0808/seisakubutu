import random

# ビンゴカードの生成
def generate_bingo_card():
    card = []
    for _ in range(5):
        row = random.sample(range(1, 16), 5)
        card.append(row)
    return card

# ビンゴカードの表示
def print_bingo_card(card):
    for row in card:
        print(row)

bingo_card = generate_bingo_card()
print_bingo_card(bingo_card)
