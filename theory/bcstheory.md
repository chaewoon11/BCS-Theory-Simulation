# BCS Theory

표기는 M. Tinkham, *Introduction to Superconductivity* (2nd ed.)를 따른다.
(Tinkham은 생성 연산자를 $c^{*}$로 쓰지만, 여기서는 $c^{\dagger}$로 쓴다.)

## 1. BCS 해밀토니언 (pairing Hamiltonian)

BCS 이론은 운동량과 스핀이 반대인 전자쌍 $(\mathbf{k}\uparrow, -\mathbf{k}\downarrow)$ 사이의 상호작용만 남긴
축약된(reduced) 해밀토니언에서 출발한다.

$$
\mathcal{H} = \sum_{\mathbf{k}\sigma} \epsilon_{\mathbf{k}}\, n_{\mathbf{k}\sigma}
+ \sum_{\mathbf{k}\mathbf{l}} V_{\mathbf{k}\mathbf{l}}\,
c^{\dagger}_{\mathbf{k}\uparrow} c^{\dagger}_{-\mathbf{k}\downarrow}
c_{-\mathbf{l}\downarrow} c_{\mathbf{l}\uparrow}
$$

| 기호 | 의미 |
|---|---|
| $\epsilon_{\mathbf{k}}$ | 단일입자(Bloch) 에너지 |
| $c^{\dagger}_{\mathbf{k}\sigma},\ c_{\mathbf{k}\sigma}$ | 운동량 $\mathbf{k}$, 스핀 $\sigma$ 전자의 생성 / 소멸 연산자 |
| $n_{\mathbf{k}\sigma} = c^{\dagger}_{\mathbf{k}\sigma} c_{\mathbf{k}\sigma}$ | 개수 연산자 |
| $V_{\mathbf{k}\mathbf{l}}$ | 쌍 $(\mathbf{l}\uparrow, -\mathbf{l}\downarrow)$를 쌍 $(\mathbf{k}\uparrow, -\mathbf{k}\downarrow)$로 산란시키는 행렬 요소 |

- 첫째 항: 자유 전자의 운동 에너지
- 둘째 항: 쌍 산란 $(\mathbf{l}\uparrow, -\mathbf{l}\downarrow) \to (\mathbf{k}\uparrow, -\mathbf{k}\downarrow)$.
  운동량 전달량은 $\mathbf{q} = \mathbf{k} - \mathbf{l}$ 이다.

**부호 규약:** $V_{\mathbf{k}\mathbf{l}} < 0$ 이 **인력**이다.

### 화학 퍼텐셜을 포함한 형태

입자 수가 고정되지 않은 BCS 시험 파동함수를 다루기 위해 $\mathcal{H} - \mu N$ 을 쓴다.
$N = \sum_{\mathbf{k}\sigma} n_{\mathbf{k}\sigma}$, 그리고 Fermi 준위에서 잰 에너지

$$
\xi_{\mathbf{k}} \equiv \epsilon_{\mathbf{k}} - \mu
$$

를 쓰면

$$
\mathcal{H} - \mu N = \sum_{\mathbf{k}\sigma} \xi_{\mathbf{k}}\, n_{\mathbf{k}\sigma}
+ \sum_{\mathbf{k}\mathbf{l}} V_{\mathbf{k}\mathbf{l}}\,
c^{\dagger}_{\mathbf{k}\uparrow} c^{\dagger}_{-\mathbf{k}\downarrow}
c_{-\mathbf{l}\downarrow} c_{\mathbf{l}\uparrow}
$$

이다.

> 이 프로젝트에서는 $V_{\mathbf{k}\mathbf{l}}$ 을 교과서의 상수 근사로 고정하지 않고 일반적인 형태로 둔다.
