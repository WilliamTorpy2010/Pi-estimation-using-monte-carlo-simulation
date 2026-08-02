# Pi-estimation-using-monte-carlo-simulation, runs 10,000 simulation and generates 1000 random points per simulation, estimates pi using the ratio between how points lie in a quarter circle

import random
import math

number_simulations = 10000
number_points = 1000

estimates = []

for simulation in range(number_simulations):
    points_inside = 0

    for _ in range(number_points):
        x = random.random()
        y = random.random()

        if x**2 + y**2 <= 1:
            points_inside += 1

    pi_estimate = (points_inside / number_points) * 4
    estimates.append(pi_estimate)

mean_estimate = sum(estimates) / number_simulations

error = abs(math.pi - mean_estimate)

print("Pi calculator using Monte Carlo simulation")
print("Simulations:", number_simulations)
print("Points per simulation:", number_points)
print("Estimated value of Pi:", mean_estimate)
print("Error:", error)
