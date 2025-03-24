# 水平分层模型下地震波反射/折射系数的详细推导

---

## 1. 基本方程与势函数表达

在弹性介质中，位移场 $\mathbf{u}$ 可分解为 **标量势 $\phi$（对应P波）** 和 **矢量势 $\mathbf{\psi}$（对应S波）**，满足：

$$
\mathbf{u} = \nabla \phi + \nabla \times \mathbf{\psi}, \quad \nabla \cdot \mathbf{\psi} = 0
$$

对于 **P-SV波系统**（二维平面问题），设 $\mathbf{\psi} = (0, \psi, 0)$，则位移分量可写为：

$$
u_x = \frac{\partial \phi}{\partial x} - \frac{\partial \psi}{\partial z}, \quad u_z = \frac{\partial \phi}{\partial z} + \frac{\partial \psi}{\partial x}
$$

应力分量由广义胡克定律给出：

$$
\tau_{zz} = \lambda (\nabla \cdot \mathbf{u}) + 2\mu \frac{\partial u_z}{\partial z}
$$

$$
\tau_{xz} = \mu \left( \frac{\partial u_x}{\partial z} + \frac{\partial u_z}{\partial x} \right)
$$

---

## 2. P-SV波系统的反射/透射系数推导

### 2.1 波场分解与势函数表达

假设平面波入射到水平界面 $z=0$，上层介质参数为 $\alpha_1, \beta_1, \rho_1$，下层为 $\alpha_2, \beta_2, \rho_2$。波场由以下势函数组成：

- **入射P波**：

$$
\phi^{(i)} = A_1 e^{i(k_x x - k_{zP1} z)}
$$

- **反射P波**：

$$
\phi^{(r)} = R_{PP} A_1 e^{i(k_x x + k_{zP1} z)}
$$

- **反射SV波**：

$$
\psi^{(r)} = R_{PS} A_1 e^{i(k_x x + k_{zS1} z)}
$$

- **透射P波**：

$$
\phi^{(t)} = T_{PP} A_1 e^{i(k_x x - k_{zP2} z)}
$$

- **透射SV波**：

$$
\psi^{(t)} = T_{PS} A_1 e^{i(k_x x - k_{zS2} z)}
$$

其中：
- 水平波数：

$$
k_x = \frac{\omega \sin \theta}{\alpha_1} \quad (\text{Snell定律})
$$

- 垂直波数：

$$
k_{zP} = \sqrt{\frac{\omega^2}{\alpha^2} - k_x^2}, \quad k_{zS} = \sqrt{\frac{\omega^2}{\beta^2} - k_x^2}
$$

---

### 2.2 边界条件

在界面 $z=0$ 处，位移和应力连续：

1. **位移连续**：
- 水平分量：

$$
u_x^{(1)} = u_x^{(2)}
$$

- 垂直分量：

$$
u_z^{(1)} = u_z^{(2)}
$$

2. **应力连续**：
- 正应力：
     
$$
\tau_{zz}^{(1)} = \tau_{zz}^{(2)}
$$

- 切应力：

$$
\tau_{xz}^{(1)} = \tau_{xz}^{(2)}
$$

---

### 2.3 位移与应力的具体表达式

将势函数代入位移和应力表达式：

- **位移分量**：

$$
u_x = i k_x (\phi + \psi) + \frac{\partial \psi}{\partial z}
$$

$$
u_z = \frac{\partial \phi}{\partial z} + i k_x \psi
$$

- **正应力 $\tau_{zz}$**：

$$
\tau_{zz} = \lambda \nabla^2 \phi + 2\mu \left( \frac{\partial^2 \phi}{\partial z^2} + \frac{\partial^2 \psi}{\partial x \partial z} \right)
$$

- **切应力 $\tau_{xz}$**：

$$
\tau_{xz} = \mu \left( 2 \frac{\partial^2 \phi}{\partial x \partial z} + \frac{\partial^2 \psi}{\partial x^2} - \frac{\partial^2 \psi}{\partial z^2} \right)
$$

---

### 2.4 建立方程组

在 $z=0$ 处，将总位移和总应力（入射+反射）与透射场代入边界条件，得到四元线性方程组(Zoeppritz方程)：

$$
(1 + R_{PP}) \sin\theta_p + R_{PS} \cos\theta_s = T_{PP} \sin\theta_p^{'} + T_{PS} \cos\theta_s^{'} 
$$

$$
(1 - R_{PP}) \cos\theta_p + R_{PS} \sin\theta_s = \frac{\rho_2 \alpha_2}{\rho_1 \alpha_1} T_{PP} \cos\theta_p^{'} - \frac{\rho_2 \beta_2}{\rho_1 \alpha_1} T_{PS} \sin\theta_s^{'} 
$$

$$
\rho_1 \alpha_1 (1 + R_{PP}) \cos 2\theta_s - \rho_1 \beta_1 R_{PS} \sin 2\theta_s = \rho_2 \alpha_2 T_{PP} \cos 2\theta_s^{'} + \rho_2 \beta_2 T_{PS} \sin 2\theta_s^{'} 
$$

$$
\rho_1 \beta_1 (1 - R_{PP}) \sin 2\theta_p + \rho_1 \beta_1 R_{PS} \cos 2\theta_s = \rho_2 \beta_2 T_{PP} \sin 2\theta_p^{'} + \rho_2 \beta_2 T_{PS} \cos 2\theta_s^{'}
$$

---

### 2.5 矩阵形式与Zoeppritz方程

将方程组整理为矩阵形式：

$$
\mathbf{M} \mathbf{x} = \mathbf{b}
$$

其中：
- $\mathbf{x} = [R_{PP}, R_{PS}, T_{PP}, T_{PS}]^T$
- $\mathbf{M}$ 是 $4 \times 4$ 系数矩阵，包含介质参数和角度信息
- $\mathbf{b}$ 是入射波相关的向量

---

## 3. SH波系统的反射/透射系数推导

对于 **SH波**，位移仅存在横向分量 $u_y$，边界条件简化为：

1. **位移连续**：$u_y^{(1)} = u_y^{(2)}$
2. **切应力连续**：$\tau_{yz}^{(1)} = \tau_{yz}^{(2)}$

设入射SH波振幅为1，反射系数为 $R_{SH}$，透射系数为 $T_{SH}$，则：

- **位移场**：

$$
u_y^{(1)} = e^{i(k_x x - k_{zS1} z)} + R_{SH} e^{i(k_x x + k_{zS1} z)}, \quad u_y^{(2)} = T_{SH} e^{i(k_x x - k_{zS2} z)}
$$

- **切应力**：

$$
\tau_{yz} = \mu \frac{\partial u_y}{\partial z} = \mu \left( -i k_{zS1} e^{-i k_{zS1} z} + i k_{zS1} R_{SH} e^{i k_{zS1} z} \right)
$$

在 $z=0$ 处联立方程：

$$
\begin{cases}
1 + R_{SH} = T_{SH} \\
\mu_1 k_{zS1} (1 - R_{SH}) = \mu_2 k_{zS2} T_{SH}
\end{cases}
$$

解得：

$$
R_{SH} = \frac{\mu_1 k_{zS1} - \mu_2 k_{zS2}}{\mu_1 k_{zS1} + \mu_2 k_{zS2}}, \quad T_{SH} = \frac{2 \mu_1 k_{zS1}}{\mu_1 k_{zS1} + \mu_2 k_{zS2}}
$$

代入 $\mu = \rho \beta^2$ 和 $k_{zS} = \frac{\omega \cos\theta}{\beta}$，最终得到：

$$
R_{SH} = \frac{\rho_1 \beta_1 \cos\theta_1 - \rho_2 \beta_2 \cos\theta_2}{\rho_1 \beta_1 \cos\theta_1 + \rho_2 \beta_2 \cos\theta_2}, \quad T_{SH} = \frac{2 \rho_1 \beta_1 \cos\theta_1}{\rho_1 \beta_1 \cos\theta_1 + \rho_2 \beta_2 \cos\theta_2}
$$

---

## 4. 物理意义与参数分析

- **P-SV系统**：反射/透射系数由介质阻抗($\rho \alpha$, $\rho \beta$)和入射角共同决定，涉及波型转换(P↔SV)。
- **SH系统**：仅与横波阻抗 $\rho \beta \cos\theta$ 的差异有关，无波型转换。


