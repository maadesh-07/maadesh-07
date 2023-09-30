import random
import time

# Simulated parking lot with 10 parking spaces
total_spaces = 10
occupied_spaces = 0

def check_availability():
    global occupied_spaces
    return random.choice([True, False])  # Simulate space availability randomly

def update_display():
    print(f"Total Spaces: {total_spaces}")
    print(f"Occupied Spaces: {occupied_spaces}")
    print(f"Available Spaces: {total_spaces - occupied_spaces}")
    print()

def simulate_smart_parking():
    global occupied_spaces
    while True:
        # Check for space availability
        if check_availability():
            if occupied_spaces < total_spaces:
                occupied_spaces += 1
                print("Car parked successfully!")
            else:
                print("Parking lot is full. Cannot park.")
        else:
            if occupied_spaces > 0:
                occupied_spaces -= 1
                print("Car left. Space freed up.")
            else:
                print("No cars in the parking lot.")

        update_display()
        time.sleep(2)  # Simulate parking status updates every 2 seconds

if __name__ == "__main__":
    print("Smart Parking System Simulation\n")
    simulate_smart_parking()
