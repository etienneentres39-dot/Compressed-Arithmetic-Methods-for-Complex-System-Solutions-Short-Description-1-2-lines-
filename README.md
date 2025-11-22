About Me

I develop compressed arithmetic methods to solve complex systems quickly and accurately, including 1D and 2D wave equations. My approach generates verified outputs and visualizations while keeping my private intuition secure.

Key Formulas:

1D Wave:

𝜓
𝑖
𝑡
+
1
=
2
𝜓
𝑖
𝑡
−
𝜓
𝑖
𝑡
−
1
+
𝑘
(
𝜓
𝑖
+
1
𝑡
−
2
𝜓
𝑖
𝑡
+
𝜓
𝑖
−
1
𝑡
)
ψ
i
t+1
	​

=2ψ
i
t
	​

−ψ
i
t−1
	​

+k(ψ
i+1
t
	​

−2ψ
i
t
	​

+ψ
i−1
t
	​

)

2D Wave:

𝜓
𝑖
,
𝑗
𝑡
+
1
=
2
𝜓
𝑖
,
𝑗
𝑡
−
𝜓
𝑖
,
𝑗
𝑡
−
1
+
𝑘
[
(
𝜓
𝑖
+
1
,
𝑗
𝑡
+
𝜓
𝑖
−
1
,
𝑗
𝑡
+
𝜓
𝑖
,
𝑗
+
1
𝑡
+
𝜓
𝑖
,
𝑗
−
1
𝑡
)
−
4
𝜓
𝑖
,
𝑗
𝑡
]
ψ
i,j
t+1
	​

=2ψ
i,j
t
	​

−ψ
i,j
t−1
	​

+k[(ψ
i+1,j
t
	​

+ψ
i−1,j
t
	​

+ψ
i,j+1
t
	​

+ψ
i,j−1
t
	​

)−4ψ
i,j
t
	​

]

Example Python (1D wave):

import numpy as np

Nx, Nt = 10, 20
c, dx, dt = 1, 0.1, 0.1
k = (c*dt/dx)**2

psi = np.zeros((Nx, Nt+1))
psi[:,0] = [0,0,0,0,0,1,0,0,0,0]
psi[:,1] = psi[:,0]

for t in range(1, Nt):
    for i in range(1, Nx-1):
        psi[i,t+1] = 2*psi[i,t] - psi[i,t-1] + k*(psi[i+1,t] - 2*psi[i,t] + psi[i-1,t])

print(psi)
