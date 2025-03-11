### **Part 1 推导射线路径方程**

---

#### **步骤1：从 Eikonal 方程出发**

Eikonal 方程为：

$$
|\nabla T| = \frac{1}{c(\mathbf{x})}
$$

其中 $T(\mathbf{x})$ 是波前到达点 $\mathbf{x}$ 的时间, $c(\mathbf{x})$ 是介质的速度。

---

#### **步骤2：射线路径的参数化**

射线路径以弧长 $s$ 为参数，表示为 $\overrightarrow{x}(s)$，其切向量为 $\frac{d\overrightarrow{x}}{ds}$。根据几何光学，射线方向与波前垂直，即：

$$
\frac{d\overrightarrow{x}}{ds} = c \nabla T
$$

---

#### **步骤3：对切向量求导**

对切向量方程两边关于 $s$ 求导：

$$
\frac{d}{ds} \left( \frac{1}{c} \frac{d\overrightarrow{x}}{ds} \right) = \frac{d}{ds} (\nabla T)
$$

利用链式法则展开右边：

$$
\frac{d}{ds} (\nabla T) = \nabla \left( \frac{dT}{ds} \right)
$$

注：该式证明

**证明步骤：**
对LHS

$$
\frac{d}{ds} (\nabla T) =\frac{d}{ds} \left(\frac{\partial T}{\partial x_i}(\overrightarrow{x}(s))\right)=\sum_{j=1}^n \frac{\partial^2 T}{\partial x_i\partial x_j}(\overrightarrow{x}(s))\frac{dx_j}{ds}\
$$ 

即：

$$
\frac{d}{ds} (\nabla T) = \nabla^2 T(\overrightarrow{x}(s))\ \frac{d\overrightarrow{x}}{ds}\
$$

对RHS

$$
\nabla\left(\frac{dT}{ds}\right)=\frac{\partial}{\partial x_i}\left(\frac{dT}{ds}\right)= \frac{\partial}{\partial x_i}\left(\sum_{j=1}^n \frac{\partial T}{\partial x_j}(\overrightarrow{x}(s))\frac{dx_j}{ds}\right)\
$$ 

由于 $\frac{dx_j}{ds}$ 是沿曲线参数 $s$ 的函数，而非空间坐标 $x_i$ 的函数，所以对 $x_i$ 求偏导为0

因此

$$
\nabla\left(\frac{dT}{ds}\right)=\nabla^2 T(\overrightarrow{x}(s))\ \frac{d\overrightarrow{x}}{ds}\
$$


由于 $dT/ds = \nabla T \cdot \frac{d\overrightarrow{x}}{ds} = \nabla T \cdot (c \nabla T) = c |\nabla T|^2 = \frac{1}{c}$，因此：

$$
\nabla \left( \frac{dT}{ds} \right) = \nabla \left( \frac{1}{c} \right)
$$

---

#### **步骤4：得到射线路径方程**

最终得到：

$$
\frac{d}{ds} \left( \frac{1}{c} \frac{d\mathbf{x}}{ds} \right) = \nabla \left( \frac{1}{c} \right)
$$

即射线路径的微分方程。

---

### **Part 2 推导 1D 层状介质中的射线参数与时距方程**

---

#### **假设条件**
- 速度仅随深度变化: $c=c(x_3)$
- 射线在 $x_1$ - $x_3$ 平面传播，无 $x_2$ 分量。

---

#### **步骤1：射线路径方程的分量形式**

将射线方程分解为水平和垂直分量：

**水平方向( $x_1$ )**：

$$
\frac{d}{ds} \left( \frac{1}{c} \frac{dx_1}{ds} \right) = \frac{\partial}{\partial x_1} \left( \frac{1}{c} \right) = 0
$$
   
因此：

$$
\frac{1}{c} \frac{dx_1}{ds} = p \quad (\text{常数，即射线参数})
$$

**垂直方向( $x_3$ )**：

$$
\frac{d}{ds} \left( \frac{1}{c} \frac{dx_3}{ds} \right) = \frac{\partial}{\partial x_3} \left( \frac{1}{c} \right)
$$

---

#### **步骤2：射线参数的物理意义**

由水平分量方程：

$$
\frac{dx_1}{ds} = c p
$$

结合弧长约束：

$$
\left( \frac{dx_1}{ds} \right)^2 + \left( \frac{dx_3}{ds} \right)^2 = 1
$$

得：

$$
\frac{dx_3}{ds} = \sqrt{1 - (c p)^2}
$$

或定义 $\eta$ 为垂直慢度：

$$
\frac{dx_3}{ds} = \eta, \quad \eta = \sqrt{\frac{1}{c^2} - p^2}
$$

---

#### **步骤3：时间积分与水平距离**

**传播时间 $T$**：

$$
T = \int \frac{ds}{c} = \int \frac{1}{c} \sqrt{(dx_1)^2 + (dx_3)^2}
$$

利用 $dx_1 = c p  ds$ 和 $dx_3 = \eta  ds$，得：
   
$$
T = \int \left( \frac{1}{c} \cdot \frac{dx_1}{c p} \right) + \int \left( \frac{1}{c} \cdot \frac{dx_3}{\eta} \right)
$$

简化后：

$$
T = p X + \int \eta  dx_3
$$

**水平距离 $X$**：
   
$$
X = \int dx_1 = \int c p  ds = \int \frac{c p}{\eta}  dx_3
$$

---

#### **步骤4：时距方程**

最终时距方程为：

$$
T = p X + \int_{0}^{z} \eta(x_3) \, dx_3
$$

其中：
- $p$ 是射线参数（水平慢度），
- $\eta(x_3) = \sqrt{\frac{1}{c(x_3)^2} - p^2}$ 是垂直慢度。

---

### **关键公式总结**

1.**射线路径方程**：
   
$$
\frac{d}{ds} \left( \frac{1}{c} \frac{d\mathbf{x}}{ds} \right) = \nabla \left( \frac{1}{c} \right)
$$

2. **1D 层状介质时距方程**：

$$
T = p X + \int_{0}^{z} \sqrt{\frac{1}{c(x_3)^2} - p^2}  dx_3
$$

此方程广泛应用于地震波传播和射线追踪。
