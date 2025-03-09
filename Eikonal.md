好的，现在我们从 P 波的运动方程出发，推导 Eikonal 方程。整个过程需要引入**高频近似**（几何光学近似），以下是详细推导步骤：

---

### **步骤1：P 波的运动方程**

已知 P 波的标量势波动方程为：

$$
\frac{\partial^2 \phi}{\partial t^2} = c^2 \nabla^2 \phi \quad (c = v_p)
$$

目标是找到波传播的相位规律，即 **Eikonal 方程**。

---

### **步骤2：假设解的形式（高频近似）**

假设解的形式为**振幅缓慢变化**的平面波，即：

$$
\phi(\mathbf{r}, t) = A(\mathbf{r}) e^{i \theta(\mathbf{r}, t)}
$$

其中：
- $A(\mathbf{r})$ 是振幅函数，随空间缓慢变化，
- $\theta(\mathbf{r}, t)$ 是相位函数，随时间和空间快速变化。

在**高频近似**下，相位的振荡速度远大于振幅的变化速度。具体来说：
- 振幅的二阶导数 $\nabla^2 A$ 远小于相位的导数项（如 $(\nabla \theta)^2 A$），
- 时间导数 $\frac{\partial \theta}{\partial t}$ 对应高频振荡。

---

### **步骤3：计算各阶导数**

将假设解代入波动方程，需要计算时间导数和空间导数。

#### **1. 时间二阶导数**

$$
\frac{\partial^2 \phi}{\partial t^2} = A \frac{\partial^2}{\partial t^2} e^{i \theta} = A \left[ i \frac{\partial^2 \theta}{\partial t^2} - \left(\frac{\partial \theta}{\partial t}\right)^2 \right] e^{i \theta}
$$

#### **2. 空间拉普拉斯算子 $\nabla^2 \phi$**

- 梯度项：

$$
\nabla \phi = (\nabla A) e^{i \theta} + i A (\nabla \theta) e^{i \theta}
$$

- 拉普拉斯算子：

$$
\nabla^2 \phi = \nabla \cdot (\nabla \phi) = \left[ \nabla^2 A + 2i (\nabla A \cdot \nabla \theta) + i A \nabla^2 \theta - A (\nabla \theta)^2 \right] e^{i \theta}
$$

---

### **步骤4：代入波动方程**

将时间导数和空间导数代入原方程：

$$
A \left[ i \frac{\partial^2 \theta}{\partial t^2} - \left(\frac{\partial \theta}{\partial t}\right)^2 \right] e^{i \theta} = c^2 \left[ \nabla^2 A + 2i (\nabla A \cdot \nabla \theta) + i A \nabla^2 \theta - A (\nabla \theta)^2 \right] e^{i \theta}
$$

两边除以 $e^{i \theta}$ 后得：

$$
A \left[ i \frac{\partial^2 \theta}{\partial t^2} - \left(\frac{\partial \theta}{\partial t}\right)^2 \right] = c^2 \left[ \nabla^2 A + 2i (\nabla A \cdot \nabla \theta) + i A \nabla^2 \theta - A (\nabla \theta)^2 \right]
$$

---

### **步骤5：分离实部和虚部**

将方程分为实部和虚部分别相等：

#### **1. 实部方程**

$$
-A \left(\frac{\partial \theta}{\partial t}\right)^2 = c^2 \left[ \nabla^2 A - A (\nabla \theta)^2 \right]
$$

#### **2. 虚部方程**

$$
A \frac{\partial^2 \theta}{\partial t^2} = c^2 \left[ 2 (\nabla A \cdot \nabla \theta) + A \nabla^2 \theta \right]
$$

---

### **步骤6：高频近似下的简化**

在高频近似中，假设：
1. **振幅变化缓慢**：
$\nabla^2 A \ll (\nabla \theta)^2 A$ ，
2. **相位振荡高频**：
$\frac{\partial \theta}{\partial t}$ 和 $\nabla \theta$ 的量级远大于其他项。

#### **对实部方程的简化**

忽略 $$\nabla^2 A$$（振幅的二阶导数项），得到：

$$
-A \left(\frac{\partial \theta}{\partial t}\right)^2 \approx -c^2 A (\nabla \theta)^2
$$

两边约去 $-A$，得到：

$$
\left(\frac{\partial \theta}{\partial t}\right)^2 = c^2 (\nabla \theta)^2
$$

即：

$$
\frac{\partial \theta}{\partial t} = \pm c |\nabla \theta|
$$

#### **对虚部方程的简化**

虚部方程描述了振幅的传输，但在高频近似下，通常只关注相位方程（Eikonal 方程），因此虚部方程可暂时忽略。

---

### **步骤7：稳态假设与 Eikonal 方程**

进一步假设**稳态条件**（如单频波 $\theta(\mathbf{r}, t) = k S(\mathbf{r}) - \omega t$），其中：
$S(\mathbf{r})$ 是空间相位函数，
$\omega$ 是角频率，
$k = \omega/c$ 是波数。

代入稳态相位后：

$$
\frac{\partial \theta}{\partial t} = -\omega, \quad \nabla \theta = k \nabla S
$$

代入实部简化后的方程：

$$
(-\omega)^2 = c^2 (k \nabla S)^2
$$

即：

$$
\omega^2 = c^2 k^2 (\nabla S)^2
$$

由于 $k = \omega/c$，代入后得：

$$
(\nabla S)^2 = \frac{1}{c^2}
$$

即 **Eikonal 方程**：

$$
|\nabla S| = \frac{1}{c}
$$

---

### **关键近似总结**

1. **高频近似**：假设相位 $\theta$ 变化远快于振幅 $A$，从而忽略振幅的二阶导数 $\nabla^2 A$。
2. **稳态条件**：假设相位可分离为空间和时间的线性组合（单频波）。
3. **忽略虚部方程**：仅关注相位传播规律，暂不分析振幅传输。

---

### **物理意义**

Eikonal 方程

$$
|\nabla S| = \frac{1}{c}
$$

描述了波前 $S(\mathbf{r}) = \text{常数}$ 的传播：
- 波前的法线方向为 $\nabla S$，
- 波前的传播速度为 $c$。

此方程是地震波射线理论（如斯涅尔定律）和几何光学的基础。
