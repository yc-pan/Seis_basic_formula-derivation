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
\frac{d}{ds} \left( \frac{1}{c} \frac{d\overrightarrow{x}}{ds} \right) = \nabla \left( \frac{1}{c} \right)
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
### **Part 3 推导球状分层介质中的时距方程**
---

#### **步骤1：球坐标系下的 Eikonal 方程与射线路径**

在球对称模型中，速度仅随半径 $r$ 变化，即

$$
c = c(r)
$$

波前时间

$$
T(r, \theta, \phi)
$$

仅依赖于半径 $r$ 和角度 $\theta$ (假设射线在赤道平面内传播，无 $\phi$ 依赖)。Eikonal 方程为：

$$
|\nabla T| = \frac{1}{c(r)}.
$$

在球坐标系中，梯度算符为:

$$
\nabla T = \frac{\partial T}{\partial r} \overrightarrow{e_r} + \frac{1}{r} \frac{\partial T}{\partial \theta} \overrightarrow{e}_\theta
$$

由于对称性，假设射线路径在赤道平面内($\theta$ 方向)，因此：

$$
|\nabla T| = \sqrt{\left(\frac{\partial T}{\partial r}\right)^2 + \left(\frac{1}{r} \frac{\partial T}{\partial \theta}\right)^2} = \frac{1}{c(r)}.
$$

---

#### **步骤2：守恒量（射线参数 $p$）**

定义射线参数 $p$ 为角向慢度的守恒量：

$$
p = r \cdot \frac{\partial T}{\partial \theta}.
$$

由 Eikonal 方程：

$$
\left(\frac{\partial T}{\partial r}\right)^2 + \left(\frac{p}{r}\right)^2 = \frac{1}{c(r)^2}.
$$

令 **垂直慢度**

$$
\eta(r) = \sqrt{\frac{1}{c(r)^2} - \frac{p^2}{r^2}},
$$

则有

$$
\frac{\partial T}{\partial r} = \eta(r).
$$

---

#### **步骤3：时间积分 $T$**

总传播时间 $T$ 沿射线路径为：

$$
T = \int \frac{ds}{c(r)} = \int \frac{\sqrt{dr^2 + r^2 d\theta^2}}{c(r)}.
$$

将路径分解为径向和角向部分，利用守恒量

$$
p = r \cdot \frac{\partial T}{\partial \theta},
$$

得：

$$
d\theta = \frac{p}{r^2 \eta(r)} dr.
$$

代入 $T$ 的积分：

$$
T = \int \frac{1}{c(r)} \sqrt{1 + r^2 \left(\frac{d\theta}{dr}\right)^2} dr
  = \int \frac{1}{c(r)} \sqrt{1 + \frac{p^2}{r^2 \eta(r)^2}} dr.
$$

简化被积函数：

$$
\sqrt{1 + \frac{p^2}{r^2 \eta(r)^2}} = \sqrt{\frac{1}{c(r)^2 \eta(r)^2}} = \frac{1}{c(r)\eta(r)}.
$$

因此：

$$
T = \int \frac{1}{c(r)^2 \eta(r)} dr.
$$

---

#### **步骤4：水平距离 $\Delta$ 与时间分解**

水平角距离 $\Delta$ 为射线路径的角向总位移：

$$
\Delta = 2 \int_{\text{路径}} d\theta = 2 \int_{r_0}^{r} \frac{p}{r^2 \eta(r)} dr,
$$

其中 $r_0$ 是射线的最低点（此时 $\frac{dr}{d\theta} = 0$，即 $\eta(r_0)=0$）。

将时间 $T$ 表达为：

$$
T = p \Delta + 2 \int_{r_0}^{r} \frac{\eta(r)}{r} dr.
$$

---

#### **推导细节**

1. **时间分解**：  
   利用积分技巧，将 $T$ 分解为与水平距离 $\Delta$ 相关的项和剩余积分项：
   
$$
T = \int \frac{1}{c(r)^2 \eta(r)} dr = \int \left( \frac{p^2}{r^2\,\eta(r)} + \eta(r) \right) dr.
$$

   分离后：
   
$$
T = p \cdot \underbrace{\int \frac{p}{r^2 \eta(r)}\,dr}_{\Delta/2} + \int \eta(r) dr.
$$

   结合上下限对称性（射线往返），引入因子 2，得到：
   
$$
T = p \Delta + 2 \int_{r_0}^{r} \frac{\eta(r)}{r} dr.
$$

3. **几何意义**：  
   - $p \Delta$ 表示沿水平角距离的延迟；  
   - $2 \int (\eta/r) dr$ 表示垂直路径的贡献。

---

### **最终球状模型时距方程**

$$
T = p \Delta + 2 \int_{r_0}^{r} \frac{\eta(r)}{r} dr, \quad \eta(r) = \sqrt{\frac{1}{c(r)^2} - \frac{p^2}{r^2}}.
$$

---

### **关键点总结**

1. **球对称性**：速度仅随半径 $r$ 变化，射线在赤道平面内传播。
2. **守恒量 $p$**：角向慢度
   
$$
p = r \cdot \frac{\partial T}{\partial \theta}
$$

   沿射线保持不变。
3. **积分分解**：通过分离水平与垂直贡献，得到时距方程的球面形式。


---

### **关键公式总结**

1.**射线路径方程**：
   
$$
\frac{d}{ds} \left( \frac{1}{c} \frac{d\mathbf{x}}{ds} \right) = \nabla \left( \frac{1}{c} \right)
$$

2.**1D 层状介质时距方程**：

$$
T = p X + \int_{0}^{z} \sqrt{\frac{1}{c(x_3)^2} - p^2}  dx_3
$$

3.**1D 球状介质时距方程**：

$$
T = p \Delta + 2 \int_{r_0}^{r} \frac{\eta(r)}{r} dr, \quad \eta(r) = \sqrt{\frac{1}{c(r)^2} - \frac{p^2}{r^2}}.
$$
