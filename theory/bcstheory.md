# BCS Theory

Main reference: M. Tinkham, *Introduction to Superconductivity* (2nd ed.).

## 1. BCS Hamiltonian 

BCS theory starts from a reduced Hamiltonian that keeps only the interaction between
electron pairs with opposite momentum and spin, $`(\mathbf{k}\uparrow, -\mathbf{k}\downarrow)`$.

```math
\begin{aligned}
\mathcal{H} &= \sum_{\mathbf{k}\sigma} \epsilon_{\mathbf{k}}\, n_{\mathbf{k}\sigma} \\
&\quad + \sum_{\mathbf{k}\mathbf{l}} V_{\mathbf{k}\mathbf{l}}\,
c^{\dagger}_{\mathbf{k}\uparrow} c^{\dagger}_{-\mathbf{k}\downarrow}
c_{-\mathbf{l}\downarrow} c_{\mathbf{l}\uparrow}
\end{aligned}
```

| Symbol | Meaning |
|---|---|
| $`\epsilon_{\mathbf{k}}`$ | Single-particle (Bloch) energy |
| $`c^{\dagger}_{\mathbf{k}\sigma},\ c_{\mathbf{k}\sigma}`$ | Creation / annihilation operators for an electron with momentum $`\mathbf{k}`$ and spin $`\sigma`$ |
| $`n_{\mathbf{k}\sigma} = c^{\dagger}_{\mathbf{k}\sigma} c_{\mathbf{k}\sigma}`$ | Number operator |
| $`V_{\mathbf{k}\mathbf{l}}`$ | Matrix element that scatters the pair $`(\mathbf{l}\uparrow, -\mathbf{l}\downarrow)`$ into the pair $`(\mathbf{k}\uparrow, -\mathbf{k}\downarrow)`$ |

- First term: kinetic energy of the free electrons
- Second term: pair scattering $`(\mathbf{l}\uparrow, -\mathbf{l}\downarrow) \to (\mathbf{k}\uparrow, -\mathbf{k}\downarrow)`$,
  with momentum transfer $`\mathbf{q} = \mathbf{k} - \mathbf{l}`$.

$`V_{\mathbf{k}\mathbf{l}} < 0`$ means attractive interation.

### Form including the chemical potential

Because the BCS trial wavefunction does not have a fixed particle number, we work with $`\mathcal{H} - \mu N`$.
With $`N = \sum_{\mathbf{k}\sigma} n_{\mathbf{k}\sigma}`$ and the energy measured from the Fermi level,

```math
\xi_{\mathbf{k}} \equiv \epsilon_{\mathbf{k}} - \mu ,
```

this becomes

```math
\begin{aligned}
\mathcal{H} - \mu N &= \sum_{\mathbf{k}\sigma} \xi_{\mathbf{k}}\, n_{\mathbf{k}\sigma} \\
&\quad + \sum_{\mathbf{k}\mathbf{l}} V_{\mathbf{k}\mathbf{l}}\,
c^{\dagger}_{\mathbf{k}\uparrow} c^{\dagger}_{-\mathbf{k}\downarrow}
c_{-\mathbf{l}\downarrow} c_{\mathbf{l}\uparrow} .
\end{aligned}
```

> In this project, $`V_{\mathbf{k}\mathbf{l}}`$ is kept in a general form rather than approximating it as constant.

## 2. BCS ground state ansatz

BCS take as a variational trial state a product over all pair states $`(\mathbf{k}\uparrow, -\mathbf{k}\downarrow)`$:

```math
|\psi_G\rangle = \prod_{\mathbf{k}}
\bigl( u_{\mathbf{k}} + v_{\mathbf{k}}\, c^{\dagger}_{\mathbf{k}\uparrow} c^{\dagger}_{-\mathbf{k}\downarrow} \bigr)
|\phi_0\rangle ,
```

where $`|\phi_0\rangle`$ is the vacuum (no electrons) and the product runs over all $`M`$ allowed values $`\mathbf{k}_1, \ldots, \mathbf{k}_M`$.

Normalization $`\langle \psi_G | \psi_G \rangle = 1`$ requires, for every $`\mathbf{k}`$,

```math
|u_{\mathbf{k}}|^2 + |v_{\mathbf{k}}|^2 = 1 .
```

### Meaning of $`u_{\mathbf{k}}`$ and $`v_{\mathbf{k}}`$

- $`|v_{\mathbf{k}}|^2`$: probability that the pair state $`(\mathbf{k}\uparrow, -\mathbf{k}\downarrow)`$ is **occupied**
- $`|u_{\mathbf{k}}|^2 = 1 - |v_{\mathbf{k}}|^2`$: probability that it is **empty**
- Each pair state is either doubly occupied or empty, so only the pair correlation enters the state.

### Phase convention

Only the relative phase of $`u_{\mathbf{k}}`$ and $`v_{\mathbf{k}}`$ is physical. Following Tinkham, take $`u_{\mathbf{k}}`$ real and positive and let

```math
v_{\mathbf{k}} = |v_{\mathbf{k}}|\, e^{i\varphi} .
```

For a uniform ground state the phase $`\varphi`$ is the same for all $`\mathbf{k}`$; this common phase is the phase of the superconducting order parameter.

### Particle number

$`|\psi_G\rangle`$ is a superposition of states with different numbers of pairs, so $`N`$ is not fixed. Its mean is

```math
\langle N \rangle = \sum_{\mathbf{k}\sigma} \langle n_{\mathbf{k}\sigma} \rangle
= 2 \sum_{\mathbf{k}} |v_{\mathbf{k}}|^2 ,
```

and $`\mu`$ in $`\mathcal{H} - \mu N`$ is chosen so that $`\langle N \rangle`$ equals the actual electron number $`\bar{N}`$.
For macroscopic $`\bar{N}`$ the relative fluctuation $`\delta N / \bar{N} \sim \bar{N}^{-1/2}`$ is negligible.

## 3. Variational solution at $`T = 0`$ and the gap $`\Delta_{\mathbf{k}}`$

The coefficients $`u_{\mathbf{k}}, v_{\mathbf{k}}`$ are fixed by minimizing
$`W \equiv \langle \psi_G | \mathcal{H} - \mu N | \psi_G \rangle`$.

### Variational energy

Set the common phase $`\varphi = 0`$, so $`u_{\mathbf{k}}`$ and $`v_{\mathbf{k}}`$ are real
(with general $`V_{\mathbf{k}\mathbf{l}}`$, $`\Delta_{\mathbf{k}}`$ below is then real but may change sign over $`\mathbf{k}`$).
Then

```math
\begin{aligned}
W &= 2 \sum_{\mathbf{k}} \xi_{\mathbf{k}}\, v_{\mathbf{k}}^2 \\
&\quad + \sum_{\mathbf{k}\mathbf{l}} V_{\mathbf{k}\mathbf{l}}\, u_{\mathbf{k}} v_{\mathbf{k}} u_{\mathbf{l}} v_{\mathbf{l}} .
\end{aligned}
```

The terms with $`\mathbf{k} = \mathbf{l}`$ that are not of pair-scattering form (Hartree-like terms) are omitted;
they only shift $`\xi_{\mathbf{k}}`$ and can be absorbed into it.

$`u_{\mathbf{k}}^2 + v_{\mathbf{k}}^2 = 1`$ is built in by

```math
u_{\mathbf{k}} = \sin\theta_{\mathbf{k}}, \qquad v_{\mathbf{k}} = \cos\theta_{\mathbf{k}} ,
```

which gives

```math
\begin{aligned}
W &= \sum_{\mathbf{k}} \xi_{\mathbf{k}} \bigl( 1 + \cos 2\theta_{\mathbf{k}} \bigr) \\
&\quad + \frac{1}{4} \sum_{\mathbf{k}\mathbf{l}} V_{\mathbf{k}\mathbf{l}}\, \sin 2\theta_{\mathbf{k}} \sin 2\theta_{\mathbf{l}} .
\end{aligned}
```

### Minimization

$`\partial W / \partial \theta_{\mathbf{k}} = 0`$ gives (using $`V_{\mathbf{k}\mathbf{l}} = V_{\mathbf{l}\mathbf{k}}`$)

```math
\tan 2\theta_{\mathbf{k}} = \frac{\sum_{\mathbf{l}} V_{\mathbf{k}\mathbf{l}} \sin 2\theta_{\mathbf{l}}}{2 \xi_{\mathbf{k}}} .
```

### Definition of $`\Delta_{\mathbf{k}}`$ and $`E_{\mathbf{k}}`$

```math
\boxed{\ \Delta_{\mathbf{k}} \equiv - \sum_{\mathbf{l}} V_{\mathbf{k}\mathbf{l}}\, u_{\mathbf{l}} v_{\mathbf{l}}
= - \frac{1}{2} \sum_{\mathbf{l}} V_{\mathbf{k}\mathbf{l}} \sin 2\theta_{\mathbf{l}}\ }
```

```math
E_{\mathbf{k}} \equiv \sqrt{\xi_{\mathbf{k}}^2 + \Delta_{\mathbf{k}}^2}
```

Then $`\tan 2\theta_{\mathbf{k}} = -\Delta_{\mathbf{k}} / \xi_{\mathbf{k}}`$, so

```math
\begin{aligned}
2 u_{\mathbf{k}} v_{\mathbf{k}} &= \sin 2\theta_{\mathbf{k}} = \frac{\Delta_{\mathbf{k}}}{E_{\mathbf{k}}}, \\
u_{\mathbf{k}}^2 - v_{\mathbf{k}}^2 &= -\cos 2\theta_{\mathbf{k}} = \frac{\xi_{\mathbf{k}}}{E_{\mathbf{k}}},
\end{aligned}
```

```math
\begin{aligned}
v_{\mathbf{k}}^2 &= \frac{1}{2} \Bigl( 1 - \frac{\xi_{\mathbf{k}}}{E_{\mathbf{k}}} \Bigr), \\
u_{\mathbf{k}}^2 &= \frac{1}{2} \Bigl( 1 + \frac{\xi_{\mathbf{k}}}{E_{\mathbf{k}}} \Bigr).
\end{aligned}
```

The sign is chosen so that $`v_{\mathbf{k}}^2 \to 1`$ deep below the Fermi level ($`\xi_{\mathbf{k}} \to -\infty`$).

### Gap equation ($`T = 0`$)

Substituting $`u_{\mathbf{l}} v_{\mathbf{l}} = \Delta_{\mathbf{l}} / 2E_{\mathbf{l}}`$ back into the definition of $`\Delta_{\mathbf{k}}`$:

```math
\Delta_{\mathbf{k}} = - \frac{1}{2} \sum_{\mathbf{l}} V_{\mathbf{k}\mathbf{l}}\,
\frac{\Delta_{\mathbf{l}}}{\sqrt{\xi_{\mathbf{l}}^2 + \Delta_{\mathbf{l}}^2}} .
```

This is a nonlinear integral equation for $`\Delta_{\mathbf{k}}`$ with a general kernel $`V_{\mathbf{k}\mathbf{l}}`$.
$`\Delta_{\mathbf{k}} = 0`$ (the normal state) is always a solution; a nontrivial solution requires
$`V_{\mathbf{k}\mathbf{l}}`$ to be attractive in at least some channel.

## 4. Finite temperature

At $`T > 0`$ we need the excited states as well. Following Tinkham, use the mean-field (self-consistent field)
form of the pairing Hamiltonian and diagonalize it with the Bogoliubov–Valatin transformation.

### Mean-field Hamiltonian

Define the pair amplitude

```math
b_{\mathbf{k}} \equiv \langle c_{-\mathbf{k}\downarrow} c_{\mathbf{k}\uparrow} \rangle ,
```

where $`\langle \cdots \rangle`$ is the thermal average. Writing
$`c_{-\mathbf{k}\downarrow} c_{\mathbf{k}\uparrow} = b_{\mathbf{k}} + (c_{-\mathbf{k}\downarrow} c_{\mathbf{k}\uparrow} - b_{\mathbf{k}})`$
and dropping terms quadratic in the fluctuation,

```math
\begin{aligned}
\mathcal{H}_M = \sum_{\mathbf{k}\sigma} \xi_{\mathbf{k}}\, n_{\mathbf{k}\sigma}
+ \sum_{\mathbf{k}\mathbf{l}} V_{\mathbf{k}\mathbf{l}}
\Bigl( &c^{\dagger}_{\mathbf{k}\uparrow} c^{\dagger}_{-\mathbf{k}\downarrow}\, b_{\mathbf{l}} \\
&+ b^{*}_{\mathbf{k}}\, c_{-\mathbf{l}\downarrow} c_{\mathbf{l}\uparrow} \\
&- b^{*}_{\mathbf{k}} b_{\mathbf{l}} \Bigr).
\end{aligned}
```

### General definition of $`\Delta_{\mathbf{k}}`$

```math
\boxed{\ \Delta_{\mathbf{k}} \equiv - \sum_{\mathbf{l}} V_{\mathbf{k}\mathbf{l}}\, b_{\mathbf{l}}
= - \sum_{\mathbf{l}} V_{\mathbf{k}\mathbf{l}}\, \langle c_{-\mathbf{l}\downarrow} c_{\mathbf{l}\uparrow} \rangle\ }
```

This reduces to the definition of Section 3 at $`T = 0`$, where $`b_{\mathbf{l}} = u_{\mathbf{l}} v_{\mathbf{l}}`$.
With $`V_{\mathbf{k}\mathbf{l}} = V^{*}_{\mathbf{l}\mathbf{k}}`$ (Hermitian),

```math
\begin{aligned}
\mathcal{H}_M = \sum_{\mathbf{k}\sigma} \xi_{\mathbf{k}}\, n_{\mathbf{k}\sigma}
- \sum_{\mathbf{k}} \Bigl( &\Delta_{\mathbf{k}}\, c^{\dagger}_{\mathbf{k}\uparrow} c^{\dagger}_{-\mathbf{k}\downarrow} \\
&+ \Delta^{*}_{\mathbf{k}}\, c_{-\mathbf{k}\downarrow} c_{\mathbf{k}\uparrow} \\
&- \Delta_{\mathbf{k}}\, b^{*}_{\mathbf{k}} \Bigr).
\end{aligned}
```

$`\mathcal{H}_M`$ is bilinear in the electron operators, so it can be diagonalized exactly.

### Bogoliubov–Valatin transformation

Introduce new fermion operators $`\gamma_{\mathbf{k}\uparrow}, \gamma_{-\mathbf{k}\downarrow}`$:

```math
\begin{aligned}
c_{\mathbf{k}\uparrow} &= u^{*}_{\mathbf{k}}\, \gamma_{\mathbf{k}\uparrow} + v_{\mathbf{k}}\, \gamma^{\dagger}_{-\mathbf{k}\downarrow}, \\
c^{\dagger}_{-\mathbf{k}\downarrow} &= -v^{*}_{\mathbf{k}}\, \gamma_{\mathbf{k}\uparrow} + u_{\mathbf{k}}\, \gamma^{\dagger}_{-\mathbf{k}\downarrow},
\end{aligned}
```

with $`|u_{\mathbf{k}}|^2 + |v_{\mathbf{k}}|^2 = 1`$ so that the $`\gamma`$'s obey fermion anticommutation relations.
$`\gamma^{\dagger}_{\mathbf{k}\uparrow}`$ creates a quasiparticle that carries momentum $`\mathbf{k}`$ and spin up;
$`\gamma^{\dagger}_{-\mathbf{k}\downarrow}`$ one with $`-\mathbf{k}`$ and spin down.

Choosing $`u_{\mathbf{k}}, v_{\mathbf{k}}`$ so that the terms $`\gamma^{\dagger}\gamma^{\dagger}`$ and $`\gamma\gamma`$ vanish gives

```math
\begin{aligned}
|v_{\mathbf{k}}|^2 &= \frac{1}{2} \Bigl( 1 - \frac{\xi_{\mathbf{k}}}{E_{\mathbf{k}}} \Bigr), \\
|u_{\mathbf{k}}|^2 &= \frac{1}{2} \Bigl( 1 + \frac{\xi_{\mathbf{k}}}{E_{\mathbf{k}}} \Bigr), \\
u^{*}_{\mathbf{k}} v_{\mathbf{k}} &= \frac{\Delta_{\mathbf{k}}}{2E_{\mathbf{k}}},
\end{aligned}
```

```math
E_{\mathbf{k}} = \sqrt{\xi_{\mathbf{k}}^2 + |\Delta_{\mathbf{k}}|^2} ,
```

the same form as at $`T = 0`$, and

```math
\begin{aligned}
\mathcal{H}_M &= \sum_{\mathbf{k}} \bigl( \xi_{\mathbf{k}} - E_{\mathbf{k}} + \Delta_{\mathbf{k}} b^{*}_{\mathbf{k}} \bigr) \\
&\quad + \sum_{\mathbf{k}} E_{\mathbf{k}} \bigl( \gamma^{\dagger}_{\mathbf{k}\uparrow} \gamma_{\mathbf{k}\uparrow}
+ \gamma^{\dagger}_{-\mathbf{k}\downarrow} \gamma_{-\mathbf{k}\downarrow} \bigr).
\end{aligned}
```

The first sum is the condensate energy; the second describes independent quasiparticles with excitation energy
$`E_{\mathbf{k}} \ge |\Delta_{\mathbf{k}}|`$, so $`|\Delta_{\mathbf{k}}|`$ is the energy gap at $`\mathbf{k}`$.

### Thermal occupation

Since the quasiparticles are independent fermions,

```math
\begin{aligned}
\langle \gamma^{\dagger}_{\mathbf{k}\uparrow} \gamma_{\mathbf{k}\uparrow} \rangle
&= \langle \gamma^{\dagger}_{-\mathbf{k}\downarrow} \gamma_{-\mathbf{k}\downarrow} \rangle \\
&= f(E_{\mathbf{k}}) = \frac{1}{e^{\beta E_{\mathbf{k}}} + 1},
\qquad \beta = \frac{1}{k_B T} .
\end{aligned}
```

Expressing $`b_{\mathbf{k}}`$ through the $`\gamma`$'s (terms $`\gamma\gamma`$, $`\gamma^{\dagger}\gamma^{\dagger}`$ average to zero):

```math
\begin{aligned}
b_{\mathbf{k}} &= \langle c_{-\mathbf{k}\downarrow} c_{\mathbf{k}\uparrow} \rangle \\
&= u^{*}_{\mathbf{k}} v_{\mathbf{k}}
\bigl\langle 1 - \gamma^{\dagger}_{\mathbf{k}\uparrow} \gamma_{\mathbf{k}\uparrow} - \gamma^{\dagger}_{-\mathbf{k}\downarrow} \gamma_{-\mathbf{k}\downarrow} \bigr\rangle \\
&= u^{*}_{\mathbf{k}} v_{\mathbf{k}} \bigl[ 1 - 2 f(E_{\mathbf{k}}) \bigr].
\end{aligned}
```

Thermally excited quasiparticles block pair states and reduce the pair amplitude.

### Gap equation at finite $`T`$

Using $`u^{*}_{\mathbf{l}} v_{\mathbf{l}} = \Delta_{\mathbf{l}} / 2E_{\mathbf{l}}`$ and
$`1 - 2f(E) = \tanh(\beta E / 2)`$:

```math
\boxed{\ \Delta_{\mathbf{k}} = - \sum_{\mathbf{l}} V_{\mathbf{k}\mathbf{l}}\,
\frac{\Delta_{\mathbf{l}}}{2E_{\mathbf{l}}} \tanh \frac{\beta E_{\mathbf{l}}}{2}\ }
```

```math
E_{\mathbf{l}} = \sqrt{\xi_{\mathbf{l}}^2 + |\Delta_{\mathbf{l}}|^2}
```

- As $`T \to 0`$, $`\tanh(\beta E / 2) \to 1`$ and the $`T = 0`$ gap equation of Section 3 is recovered.
- $`E_{\mathbf{l}}`$ itself depends on $`\Delta_{\mathbf{l}}`$, so the equation must be solved self-consistently at each $`T`$,
  giving $`\Delta_{\mathbf{k}}(T)`$.
- The temperature at which the nontrivial solution disappears is $`T_c`$.

### Number equation

The chemical potential is fixed by

```math
\langle N \rangle = \sum_{\mathbf{k}} \Bigl[ 1 - \frac{\xi_{\mathbf{k}}}{E_{\mathbf{k}}} \tanh \frac{\beta E_{\mathbf{k}}}{2} \Bigr] = \bar{N} .
```

When the density of states is approximately constant over the energy range where $`\Delta_{\mathbf{k}} \neq 0`$
(particle–hole symmetry around the Fermi level), $`\mu`$ is unchanged from its normal-state value and this equation can be dropped.
