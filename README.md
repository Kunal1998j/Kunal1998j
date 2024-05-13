import random

class WheelOfWins:
    def __init__(self):
        self.prizes = ["Coins", "Discounts", "Vouchers", "Special Grand Prizes"]
        self.players = {}  # Store player data {name: winnings}

    def spin_wheel(self):
        return random.choice(self.prizes)

    def add_player(self, name):
        self.players[name] = 0

    def update_score(self, name, prize):
        self.players[name] += 1

    def display_leaderboard(self):
        sorted_players = sorted(self.players.items(), key=lambda x: x[1], reverse=True)
        print("Leaderboard:")
        for i, (player, score) in enumerate(sorted_players, start=1):
            print(f"{i}. {player}: {score} wins")

# Sample usage
if __name__ == "__main__":
    game = WheelOfWins()
    game.add_player("Player 1")
    game.add_player("Player 2")

    for _ in range(5):  # Simulate 5 spins
        winner = random.choice(list(game.players.keys()))
        prize = game.spin_wheel()
        game.update_score(winner, prize)
        print(f"{winner} wins {prize}")

    game.display_leaderboard()
