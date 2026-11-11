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
