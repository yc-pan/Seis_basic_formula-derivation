# **水平层状介质与球状介质的能量通量推导**

---

## **第一部分：水平层状介质下的能量通量推导**

### **1. 射线参数与斯涅尔定律**
在水平层状介质中，地震波沿射线路径传播，遵循斯涅尔定律。射线参数 $p$（单位：s/m）定义为：

$$
p = \frac{\sin i(z)}{v(z)} = \text{常数}
$$

其中 $i(z)$ 是射线在深度 $z$ 处与垂直方向的夹角，$v(z)$ 是介质的速度。在地表（$z=0$）处，参数简化为：

$$
p = \frac{\sin i_0}{v_0}, \quad i_0 = i(z=0)
$$

---

### **2. 震中距与射线几何**
地震波从震源传播到地表，形成震中距 $X$。射线路径的水平投影长度 $X$ 是射线参数的函数：

$$
X = 2 \int_{0}^{z_{\text{max}}} \tan i(z) \, dz
$$

但由于水平层状的对称性，震中距可简化为：

$$
X = 2p \int_{0}^{z_{\text{max}}} \frac{v(z)}{\sqrt{1 - p^2 v(z)^2}} \, dz
$$

更直接的方式是通过射线参数 $p$ 与 $i_0$ 的关系，得到：

$$
X = X(p) \quad \text{和} \quad T = T(p) \quad (\text{走时})
$$

---

### **3. 波前面积与能量守恒**
能量通量 $\epsilon$ 表示单位面积上的能量密度。总能量 $k$ 分布在波前面积 $A$ 上：

$$
\epsilon = \frac{k}{A}
$$

波前面积由射线管的几何扩展决定。考虑两相邻射线在震中距 $X$ 处的微小夹角 $di_0$，对应的波前面积元素为：

$$
dA = 2\pi X \cdot \left| \frac{dX}{di_0} \right|^{-1} di_0
$$

**解释：**
- $2\pi X$：半径为 $X$ 的圆周长度（环状波前）。
- $\left| \frac{dX}{di_0} \right|^{-1}$：射线管宽度随 $di_0$ 的变化率（几何扩展因子）。

代入能量通量公式：

$$
\epsilon = \frac{k}{2\pi X \cdot \left| \frac{dX}{di_0} \right|^{-1}} = \frac{k}{2\pi} \cdot \frac{1}{X} \left| \frac{di_0}{dX} \right|
$$

---

### **4. 引入走时二阶导数**
射线参数 $p$ 与走时 $T$ 的关系为：

$$
p = \frac{dT}{dX}
$$

对 $p$ 求导得二阶导数：

$$
\frac{d^2 T}{dX^2} = \frac{dp}{dX}
$$

结合 $p = \frac{\sin i_0}{v_0}$，对 $p$ 求导：

$$
\frac{dp}{dX} = \frac{\cos i_0}{v_0} \cdot \frac{di_0}{dX}
$$

整理得：

$$
\frac{di_0}{dX} = \frac{v_0}{\cos i_0} \cdot \frac{d^2 T}{dX^2}
$$

将 $\frac{di_0}{dX}$ 代入能量通量公式：

$$
\epsilon = \frac{k}{2\pi} \cdot \frac{v_0 \tan i_0}{X \cos i_0} \left| \frac{d^2 T}{dX^2} \right|
$$

---

## **第二部分：球状介质下的能量通量推导**

### **1. 球坐标系下的射线参数**
在球状介质中，射线参数 $p$ 定义为：

$$
p = \frac{r \sin i(r)}{v(r)} = \text{常数}
$$

在地表($r = r_0$)处：

$$
p = \frac{r_0 \sin i_0}{v_0}
$$

---

### **2. 震中距与几何扩展**
震中距 $\Delta$ 以角度表示（单位：弧度）。射线路径的水平投影对应圆心角 $\Delta$，其几何关系为：

$$
\Delta = 2 \int_{r_0}^{r_{\text{min}}} \frac{p v(r)}{r \sqrt{r^2 - p^2 v(r)^2}} \, dr
$$

波前面积在球面上扩展，面积元素为：

$$
dA = 2\pi r_0^2 \sin\Delta \cdot \left| \frac{d\Delta}{di_0} \right|^{-1} di_0
$$

**解释：**
- $2\pi r_0^2 \sin\Delta$：球面上纬度为 $\Delta$ 的环带面积。
- $\left| \frac{d\Delta}{di_0} \right|^{-1}$：射线管宽度随 $di_0$ 的变化率。

---

### **3. 能量通量表达式**
能量通量为：

$$
\epsilon = \frac{k}{2\pi r_0^2 \sin\Delta \cdot \left| \frac{d\Delta}{di_0} \right|^{-1}} = \frac{k}{2\pi} \cdot \frac{\tan i_0}{r_0^2 \sin\Delta} \left| \frac{di_0}{d\Delta} \right|
$$

---

### **4. 走时导数与参数转换**
射线参数 $p$ 与走时 $T$ 的关系为：

$$
p = \frac{dT}{d\Delta}
$$

对 $p$ 求导得二阶导数：

$$
\frac{d^2 T}{d\Delta^2} = \frac{dp}{d\Delta}
$$

结合 $p = \frac{r_0 \sin i_0}{v_0}$，对 $p$ 求导：

$$
\frac{dp}{d\Delta} = \frac{r_0 \cos i_0}{v_0} \cdot \frac{di_0}{d\Delta}
$$

整理得：

$$
\frac{di_0}{d\Delta} = \frac{v_0}{r_0 \cos i_0} \cdot \frac{d^2 T}{d\Delta^2}
$$

代入能量通量公式：

$$
\epsilon = \frac{k}{2\pi} \cdot \frac{v_0 \tan i_0}{r_0^3 \sin\Delta} \left| \frac{d^2 T}{d\Delta^2} \right|
$$

---

## **关键结论对比**

| 介质类型       | 能量通量公式                                                                  | 核心变量说明                           |
|----------------|----------------------------------------------------------------------------|---------------------------------------|
| **水平层状介质** | $$\epsilon = \frac{k}{2\pi} \cdot \frac{v_0 \tan i_0}{X \cos i_0} \left| \frac{d^2 T}{dX^2} \right|$$ | $X$：线震中距，$T$：走时          |
| **球状介质**    | $$\epsilon = \frac{k}{2\pi} \cdot \frac{v_0 \tan i_0}{r_0^3 \sin\Delta} \left| \frac{d^2 T}{d\Delta^2} \right|$$ | $\Delta$：角震中距，$r_0$：地球半径 |
