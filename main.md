## Example:
Given a new vehicle with the following features: Horsepower = 180, Weight = 2800 lbs, Max Speed = 135 mph, what is the most likely class for this vehicle .

| **Instance** | **Horsepower** | **Weight (lbs)** | **Max Speed (mph)** | **Class**  |
|--------------|----------------|------------------|---------------------|------------|
| 1            | 200            | 3000             | 140                 | Car        |
| 2            | 150            | 2500             | 130                 | Car        |
| 3            | 100            | 1000             | 90                  | Motorcycle |
| 4            | 80             | 800              | 85                  | Motorcycle |
| 5            | 300            | 5000             | 120                 | Truck      |
| 6            | 250            | 4500             | 110                 | Truck      |
| 7            | 180            | 2800             | 135                 | Car        |

We want to classify a new vehicle with the following features:
Horsepower = 180, Weight = 2800 lbs, Max Speed = 135 mph.

Let's begin:

using the formula P(X) = Number of X instances / Total number of instances.

| **Vehicle** | **Number of Instances** | **Total Instances** | **Probability**             |
|-------------|-------------------------|---------------------|-----------------------------|
| Car         | 3                       | 7                   | P(Car) = 3 / 7 = 3/7        |
| Motorcycle  | 2                       | 7                   | P(Motorcycle) = 2 / 7 = 2/7 |
| Truck       | 2                       | 7                   | P(Truck) = 2 / 7 = 2/7      |

the probabilities of each feature:

\- For Horsepower:
| **Vehicle** | **Number of Instances** | **Total Instances** | **P(Horsepower = 180 \| Vehicle)** |
|-------------|-------------------------|---------------------|------------------------------------|
| Car         | 3                       | 7                   | 1/3                                |
| Motorcycle  | 2                       | 7                   | 0                                  |
| Truck       | 2                       | 7                   | 0                                  |

\- For weight,
| **Vehicle** | **Number of Instances** | **Total Instances** | **P(Weight = 2800 \| Vehicle)** |
|-------------|-------------------------|---------------------|---------------------------------|
| Car         | 3                       | 7                   | 2/3                             |
| Motorcycle  | 2                       | 7                   | 0                               |
| Truck       | 2                       | 7                   | 0                               |

\- For Max Speed:
| **Vehicle** | **Number of Instances** | **Total Instances** | **P(Max Speed = 135 \| Vehicle)** |
|-------------|-------------------------|---------------------|-----------------------------------|
| Car         | 3                       | 7                   | 1/3                               |
| Motorcycle  | 2                       | 7                   | 0                                 |
| Truck       | 2                       | 7                   | 0                                 |

\- Calculate each class:
| **Class**  | **P(Class)** | **P(180 \| Class)** | **P(2800 \| Class)** | **P(135 \| Class)** | **Posterior Probability** |
|------------|--------------|---------------------|----------------------|---------------------|---------------------------|
| Car        | 3/7          | 1/3                 | 2/3                  | 1/3                 | 2/63                      |
| Motorcycle | 2/7          | 0                   | 0                    | 0                   | 0                         |
| Truck      | 2/7          | 0                   | 0                    | 0                   | 0                         |

\- final probabilities :
| **Vehicle** | **Probability**           |
|-------------|---------------------------|
| Car         | (2/63) / (2/63 + 0 + 0)=1 |
| Motorcycle  | 0 / (2/63 + 0 + 0)=0      |
| Truck       | 0 / (2/63 + 0 + 0)=0      |

Based on the calculations, the posterior probability for the Car class
is 1, while the posterior probabilities for the Motorcycle and Truck
classes are both 0. Therefore, the most likely class for the new vehicle
with the given features is "Car."
