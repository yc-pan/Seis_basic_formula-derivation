**从拉梅方程推导出P波,S波运动方程**

---

### **步骤1：回顾拉梅方程**

弹性介质的运动方程（拉梅方程）为：

$$
\rho \frac{\partial^2 \mathbf{u}}{\partial t^2} = (\lambda + \mu) \nabla \Bigl(\nabla \cdot \mathbf{u}\Bigr) + \mu \nabla^2 \mathbf{u}
$$

其中：
- $\rho$ 是介质密度，
- $\mathbf{u}$ 是位移矢量场，
- $\lambda$ 和 $\mu$ 是拉梅常数，
- $\nabla \cdot \mathbf{u}$ 是位移场的散度，
- $\nabla^2 \mathbf{u}$ 是位移场的矢量拉普拉斯算子。

---

### **步骤2：应用亥姆霍兹分解**

根据亥姆霍兹定理，任何光滑且衰减足够快的矢量场 $\mathbf{u}$ 可以分解为无旋场（标量势 $\phi$ 的梯度）和无散场（矢量势 $\boldsymbol{\psi}$ 的旋度）之和：

$$
\mathbf{u} = \nabla \phi + \nabla \times \boldsymbol{\psi}
$$

其中：
- $\nabla \phi$ 是无旋场（满足 $\nabla \times (\nabla \phi) = 0$），
- $\nabla \times \boldsymbol{\psi}$ 是无散场（满足 $\nabla \cdot (\nabla \times \boldsymbol{\psi}) = 0$），
- 矢量势 $\boldsymbol{\psi}$ 满足规范条件 $\nabla \cdot \boldsymbol{\psi} = 0$。

---

### **步骤3：代入拉梅方程**

将

$$
\mathbf{u} = \nabla \phi + \nabla \times \boldsymbol{\psi}
$$

代入拉梅方程，得到：

$$
\rho \frac{\partial^2}{\partial t^2} \Bigl(\nabla \phi + \nabla \times \boldsymbol{\psi}\Bigr) = (\lambda + \mu) \nabla \Bigl(\nabla \cdot \bigl(\nabla \phi + \nabla \times \boldsymbol{\psi}\bigr)\Bigr) + \mu \nabla^2 \Bigl(\nabla \phi + \nabla \times \boldsymbol{\psi}\Bigr)
$$

---

### **步骤4：计算各项**

#### **1. 左边的时间导数项**

由于时间导数与梯度、旋度运算可以交换顺序，有：

$$
\rho \frac{\partial^2}{\partial t^2} \nabla \phi = \rho \nabla \Bigl( \frac{\partial^2 \phi}{\partial t^2} \Bigr), \quad \rho \frac{\partial^2}{\partial t^2} (\nabla \times \boldsymbol{\psi}) = \rho \nabla \times \Bigl( \frac{\partial^2 \boldsymbol{\psi}}{\partial t^2} \Bigr)
$$

#### **2. 右边的散度项**

- $\nabla \cdot (\nabla \phi) = \nabla^2 \phi$（标量场梯度的散度为拉普拉斯算子），
- $\nabla \cdot (\nabla \times \boldsymbol{\psi}) = 0$（旋度场的散度为零）。

因此有：

$$
(\lambda + \mu) \nabla \Bigl(\nabla \cdot \mathbf{u}\Bigr) = (\lambda + \mu) \nabla \Bigl(\nabla^2 \phi\Bigr)
$$

#### **3. 右边的拉普拉斯项**

- $\nabla^2 (\nabla \phi) = \nabla (\nabla^2 \phi)$，
- $\nabla^2 (\nabla \times \boldsymbol{\psi}) = \nabla \times (\nabla^2 \boldsymbol{\psi})$。

因此：

$$
\mu \nabla^2 \mathbf{u} = \mu \nabla (\nabla^2 \phi) + \mu \nabla \times (\nabla^2 \boldsymbol{\psi})
$$

---

### **步骤5：合并右边所有项**

将散度项与拉普拉斯项合并，得到：

$$
(\lambda + \mu) \nabla (\nabla^2 \phi) + \mu \nabla (\nabla^2 \phi) + \mu \nabla \times (\nabla^2 \boldsymbol{\psi}) = (\lambda + 2\mu) \nabla (\nabla^2 \phi) + \mu \nabla \times (\nabla^2 \boldsymbol{\psi})
$$

---

### **步骤6：等式两边分离梯度与旋度项**

拉梅方程现在写为：

$$
\rho \nabla \Bigl( \frac{\partial^2 \phi}{\partial t^2} \Bigr) + \rho \nabla \times \Bigl( \frac{\partial^2 \boldsymbol{\psi}}{\partial t^2} \Bigr) = (\lambda + 2\mu) \nabla (\nabla^2 \phi) + \mu \nabla \times (\nabla^2 \boldsymbol{\psi})
$$

由于梯度场和旋度场在适当的函数空间中是正交的，因此等式两边的梯度部分和旋度部分必须分别相等：

1. **梯度部分对应方程**：

$$
\rho \frac{\partial^2 \phi}{\partial t^2} = (\lambda + 2\mu) \nabla^2 \phi
$$

2. **旋度部分对应方程**：

$$
\rho \frac{\partial^2 \boldsymbol{\psi}}{\partial t^2} = \mu \nabla^2 \boldsymbol{\psi}
$$

---

### **步骤7：得到 P 波和 S 波的波动方程**

#### **1. P 波方程（无旋场）**

标量势 $\phi$ 满足：

$$
\frac{\partial^2 \phi}{\partial t^2} = \frac{\lambda + 2\mu}{\rho} \nabla^2 \phi
$$

波速为：

$$
v_p = \sqrt{\frac{\lambda + 2\mu}{\rho}}
$$

#### **2. S 波方程（无散场）**

矢量势 $\boldsymbol{\psi}$ 满足：

$$
\frac{\partial^2 \boldsymbol{\psi}}{\partial t^2} = \frac{\mu}{\rho} \nabla^2 \boldsymbol{\psi}
$$

波速为：

$$
v_s = \sqrt{\frac{\mu}{\rho}}
$$

---

### **关键点总结**

1. **亥姆霍兹分解**：将位移场分解为无旋（对应 P 波）和无散（对应 S 波）部分。
2. **分离变量**：利用梯度场与旋度场的正交性，将原方程分离成两个独立的方程。
3. **波动方程**：分别得到标量势 $\phi$ 和矢量势 $\boldsymbol{\psi}$ 的波动方程，从而确定 P 波与 S 波的传播特性。

通过这种分解，我们清晰地分离出弹性介质中两种独立传播的波：压缩波（P 波）和剪切波（S 波）。
