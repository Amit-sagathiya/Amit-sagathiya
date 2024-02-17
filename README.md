- 👋 Hi, I’m @Amit-sagathiya
- 👀 I’m interested in Data Analytics
- 🌱 I’m currently learning in Information and Communication Technology branch
- 💞️ I’m looking to collaborate on Data visualization and machine learning
- 📫 How to reach me amitsagathiya2003@gmail.com

<!---
Amit-sagathiya/Amit-sagathiya is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
class Rocket:
    def __init__(self):
        self.stage = "Pre-Launch"
        self.fuel = 100
        self.altitude = 0
        self.speed = 0

    def start_checks(self):
        
        if self.fuel == 100:
            return True
        else:
            return False

    def update_rocket_status(self):
        
        self.fuel -= 1
        self.altitude += 100
        self.speed += 1000

        
        if self.altitude >= 10000 and self.stage == "Stage 1":
            self.stage = "Stage 2"

        
        if self.altitude >= 20000 and self.stage == "Stage 2":
            self.stage = "Orbit"

    def fast_forward(self, seconds):
         of seconds
        for i in range(seconds):
            self.update_rocket_status()

    def __str__(self):
        return f"Stage: {self.stage}, Fuel: {self.fuel}%, Altitude: {self.altitude} km, Speed: {self.speed} km/h"


def main():
    rocket = Rocket()

    
    while True:
        
        user_input = input("> ")

        
        if user_input == "start_checks":
            if rocket.start_checks():
                print("All systems are 'Go' for launch.")
            else:
                print("Pre-launch checks failed.")
        elif user_input == "launch":
            
            while rocket.stage != "Orbit":
                rocket.update_rocket_status()
                print(rocket)

            
            if rocket.stage == "Orbit":
                print("Orbit achieved! Mission Successful.")
            else:
                print("Mission Failed due to insufficient fuel.")
        elif user_input.startswith("fast_forward"):
            
            seconds = int(user_input[13:])
            rocket.fast_forward(seconds)
            print(rocket)
        elif user_input == "quit":
            
            break
        else:
            
            print("Invalid command.")


if __name__ == "__main__":
    main()
    
