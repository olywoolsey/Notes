``` python
def freefall(n):
    """
    Plot the trajectory of an object falling freely.
    Input: n number of timesteps
    """

    tfinal = 50.0  # Select the final time
    g = 9.81  # acceleration due to gravity (m/s)
    k = 0.2  # air resistance coefficient

    # initialise time and speed arrays array
    t = np.zeros([n + 1, 1])
    s = np.zeros([n + 1, 1])

    # set initial conditions
    s[0] = 0.0
    t[0] = 0.0

    dt = (tfinal - t[0]) / n  # calculate step size

    # take n time steps, in which it is assumed that the acceleration
    # is constant in each small time interval
    for i in range(n):
        t[i + 1] = t[i] + dt
        s[i + 1] = s[i] + dt * (g - k * s[i])

    # plot output
    plt.plot(t, s, label=f"n = {n}")
```
