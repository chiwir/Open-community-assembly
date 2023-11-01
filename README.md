# Open-community-assembly

The code starts by importing necessary packages:
**numpy** is a package for scientific computing with arrays.

**matplotlib** is a package for creating visualizations.

**random** is a built-in package that can be used to generate random numbers.

**pandas** is a package for data manipulation and analysis.

**pickle** is a serialization and deserialization module that can be used to store and retrieve Python objects.

**time** is a built-in package that provides functions to work with time.

**warnings** is a built-in package that can be used to suppress warnings in the code.

Using a discretised Lotka-Volterra equation

$$ N_{i,t+1} = Poisson (\lambda_t)/J$$

$$\lambda_t =J.N_{i,t}exp(r(x_i) - \sum_{j \in S_t} \alpha_{ij}N_{j,t})$$

We consider a competitive community with **$S_t$** distinct resident species (native and non-native) at time **$t$**. Each native species i is characterized by population size, **$N_{(i,t)}$** represented by **new_N**, and , mean trait value, **$x_i$** for residents.  The population density changes for each species (resident and introduced), **$N_i$**  is are described by forms a Lotka Volterra model. The modelled community is set to start with **n = 300** number of species in a closed system.  The species are run for **start=200** before introducing new species. At **t=201**, new species are introduced continuously up to  **t=N_iter=1800** at introduction rate, **$I_t$** represented by **num**. Each introduced species, also characterized by their mean trait, are introduced in the community is characterized by time varying state variableat low density **$N_{(i,t)}$** and constant mean trait value **$x_i$**. When **$I_t =0$**, the system is closed, otherwise it is open. 

During the simulations, the code is storing data for species abundance, identities, traits and interaction strength. The data is then used to count species richness and compute richness estimators which represented by **Stab1** and **Stab2**. The traits are used to calculate functional turn uisng the RAO quandratic entropy. The species identities are used community compositional turnover using the Jaccard similarity using different lags. The species densities were used to compute Shannon and Simpson entropies.
