# oop-programming-week-5-
python programming
# Base class: Smartphone
class Smartphone:
    def __init__(self, brand, model, battery_life):
        self.brand = brand
        self.model = model
        self.battery_life = battery_life  # in hours

    def charge(self):
        print(f"{self.brand} {self.model} is charging... 🔋")

    def make_call(self, number):
        print(f"Calling {number} from {self.brand} {self.model}... 📞")

    def show_info(self):
        print(f"Brand: {self.brand}, Model: {self.model}, Battery Life: {self.battery_life} hours")

# Inherited class: GamingSmartphone
class GamingSmartphone(Smartphone):
    def __init__(self, brand, model, battery_life, has_game_mode):
        # Initialize parent class attributes
        super().__init__(brand, model, battery_life)
        self.has_game_mode = has_game_mode

    def play_game(self, game_name):
        if self.has_game_mode:
            print(f"Launching {game_name} on {self.brand} {self.model}... 🎮")
        else:
            print(f"Game mode not available on {self.brand} {self.model}. ❌")

    # Overriding the make_call method to show a gaming phone's unique functionality
    def make_call(self, number):
        print(f"Making a call in gaming mode to {number}... 📱🎮")

# Create a base Smartphone object
phone1 = Smartphone("Apple", "iPhone 14", 20)
phone1.show_info()
phone1.charge()

# Create a GamingSmartphone object
gaming_phone = GamingSmartphone("Asus", "ROG Phone 5", 12, True)
gaming_phone.show_info()
gaming_phone.play_game("PUBG Mobile")
gaming_phone.make_call("555-1234")








ctivity 2: Polymorphism Challenge!
Now, let’s create different animal classes, each with the same move() method, but each behaving differently (for example, a dog runs, a bird flies, etc.).

python
Copy
# Base class: Animal
class Animal:
    def move(self):
        pass  # This will be overridden by subclasses

# Subclass: Dog
class Dog(Animal):
    def move(self):
        print("The dog is running 🐕💨")

# Subclass: Bird
class Bird(Animal):
    def move(self):
        print("The bird is flying 🦅✈️")

# Subclass: Fish
class Fish(Animal):
    def move(self):
        print("The fish is swimming 🐟🌊")

# Create instances of each animal
dog = Dog()
bird = Bird()
fish = Fish()

# Call the move method on each instance
animals = [dog, bird, fish]

for animal in animals:
    animal.move()

