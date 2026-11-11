# BCS Theory

Notation follows M. Tinkham, *Introduction to Superconductivity* (2nd ed.).
(Tinkham writes creation operators as $c^{*}$; here we use $c^{\dagger}$.)

## 1. BCS Hamiltonian (pairing Hamiltonian)

BCS theory starts from a reduced Hamiltonian that keeps only the interaction between
electron pairs with opposite momentum and spin, $(\mathbf{k}\uparrow, -\mathbf{k}\downarrow)$.

$$
\mathcal{H} = \sum_{\mathbf{k}\sigma} \epsilon_{\mathbf{k}}\, n_{\mathbf{k}\sigma}
+ \sum_{\mathbf{k}\mathbf{l}} V_{\mathbf{k}\mathbf{l}}\,
c^{\dagger}_{\mathbf{k}\uparrow} c^{\dagger}_{-\mathbf{k}\downarrow}
c_{-\mathbf{l}\downarrow} c_{\mathbf{l}\uparrow}
$$

| Symbol | Meaning |
|---|---|
| $\epsilon_{\mathbf{k}}$ | Single-particle (Bloch) energy |
| $c^{\dagger}_{\mathbf{k}\sigma},\ c_{\mathbf{k}\sigma}$ | Creation / annihilation operators for an electron with momentum $\mathbf{k}$ and spin $\sigma$ |
| $n_{\mathbf{k}\sigma} = c^{\dagger}_{\mathbf{k}\sigma} c_{\mathbf{k}\sigma}$ | Number operator |
| $V_{\mathbf{k}\mathbf{l}}$ | Matrix element that scatters the pair $(\mathbf{l}\uparrow, -\mathbf{l}\downarrow)$ into the pair $(\mathbf{k}\uparrow, -\mathbf{k}\downarrow)$ |

- First term: kinetic energy of the free electrons
- Second term: pair scattering $(\mathbf{l}\uparrow, -\mathbf{l}\downarrow) \to (\mathbf{k}\uparrow, -\mathbf{k}\downarrow)$,
  with momentum transfer $\mathbf{q} = \mathbf{k} - \mathbf{l}$.

**Sign convention:** $V_{\mathbf{k}\mathbf{l}} < 0$ is **attractive**.

### Form including the chemical potential

Because the BCS trial wavefunction does not have a fixed particle number, we work with $\mathcal{H} - \mu N$.
With $N = \sum_{\mathbf{k}\sigma} n_{\mathbf{k}\sigma}$ and the energy measured from the Fermi level,

$$
\xi_{\mathbf{k}} \equiv \epsilon_{\mathbf{k}} - \mu ,
$$

this becomes

$$
\mathcal{H} - \mu N = \sum_{\mathbf{k}\sigma} \xi_{\mathbf{k}}\, n_{\mathbf{k}\sigma}
+ \sum_{\mathbf{k}\mathbf{l}} V_{\mathbf{k}\mathbf{l}}\,
c^{\dagger}_{\mathbf{k}\uparrow} c^{\dagger}_{-\mathbf{k}\downarrow}
c_{-\mathbf{l}\downarrow} c_{\mathbf{l}\uparrow} .
$$

> In this project, $V_{\mathbf{k}\mathbf{l}}$ is kept in a general form rather than fixed to the textbook constant approximation.

## 2. BCS ground state ansatz

BCS take as a variational trial state a product over all pair states $(\mathbf{k}\uparrow, -\mathbf{k}\downarrow)$:

$$
|\psi_G\rangle = \prod_{\mathbf{k} = \mathbf{k}_1, \ldots, \mathbf{k}_M}
\left( u_{\mathbf{k}} + v_{\mathbf{k}}\, c^{\dagger}_{\mathbf{k}\uparrow} c^{\dagger}_{-\mathbf{k}\downarrow} \right)
|\phi_0\rangle ,
$$

where $|\phi_0\rangle$ is the vacuum (no electrons) and the product runs over all $M$ allowed values of $\mathbf{k}$.

Normalization $\langle \psi_G | \psi_G \rangle = 1$ requires, for every $\mathbf{k}$,

$$
|u_{\mathbf{k}}|^2 + |v_{\mathbf{k}}|^2 = 1 .
$$

### Meaning of $u_{\mathbf{k}}$ and $v_{\mathbf{k}}$

- $|v_{\mathbf{k}}|^2$: probability that the pair state $(\mathbf{k}\uparrow, -\mathbf{k}\downarrow)$ is **occupied**
- $|u_{\mathbf{k}}|^2 = 1 - |v_{\mathbf{k}}|^2$: probability that it is **empty**
- Each pair state is either doubly occupied or empty, so only the pair correlation enters the state.

### Phase convention

Only the relative phase of $u_{\mathbf{k}}$ and $v_{\mathbf{k}}$ is physical. Following Tinkham, take $u_{\mathbf{k}}$ real and positive and let

$$
v_{\mathbf{k}} = |v_{\mathbf{k}}|\, e^{i\varphi} .
$$

For a uniform ground state the phase $\varphi$ is the same for all $\mathbf{k}$; this common phase is the phase of the superconducting order parameter.

### Particle number

$|\psi_G\rangle$ is a superposition of states with different numbers of pairs, so $N$ is not fixed. Its mean is

$$
\langle N \rangle = \sum_{\mathbf{k}\sigma} \langle n_{\mathbf{k}\sigma} \rangle
= 2 \sum_{\mathbf{k}} |v_{\mathbf{k}}|^2 ,
$$

and $\mu$ in $\mathcal{H} - \mu N$ is chosen so that $\langle N \rangle$ equals the actual electron number $\bar{N}$.
For macroscopic $\bar{N}$ the relative fluctuation $\delta N / \bar{N} \sim \bar{N}^{-1/2}$ is negligible.

### Normal-state limit

The filled Fermi sea is recovered by

$$
|v_{\mathbf{k}}| = 1,\ u_{\mathbf{k}} = 0 \quad (k < k_F), \qquad
|v_{\mathbf{k}}| = 0,\ u_{\mathbf{k}} = 1 \quad (k > k_F).
$$

In the superconducting state, $|v_{\mathbf{k}}|^2$ is smeared out around $k_F$; its shape is fixed by minimizing
$\langle \psi_G | \mathcal{H} - \mu N | \psi_G \rangle$ (next section).
