### **Dimension Compatibility Rule**

For any matrix product $XY$ to be defined, the number of columns in the first matrix $X$ must equal the number of rows in the second matrix $Y$:


$$\text{If } X \text{ is } m \times k \text{ and } Y \text{ is } k \times n\text{, then } XY \text{ is defined and has size } m \times n.$$


If the inner dimensions do not match, the product is **undefined**.

---

### **Given Dimensions**

* $A: 2 \times 3$

* $B: 3 \times 4$

* $C: 4 \times 2$

* $D: 2 \times 2$


---

### **Evaluation of Each Product**

* **$AB$**

* **Dimensions:** $(2 \times 3) \times (3 \times 4)$
* **Compatibility:** Inner dimensions match ($3 = 3$).
* **Result:** **Defined**, size is **$2 \times 4$**.


* **$BA$**

* **Dimensions:** $(3 \times 4) \times (2 \times 3)$
* **Compatibility:** Inner dimensions do not match ($4 \neq 2$).
* **Result:** **Undefined**.


* **$BC$**

* **Dimensions:** $(3 \times 4) \times (4 \times 2)$
* **Compatibility:** Inner dimensions match ($4 = 4$).
* **Result:** **Defined**, size is **$3 \times 2$**.


* **$CB$**

* **Dimensions:** $(4 \times 2) \times (3 \times 4)$
* **Compatibility:** Inner dimensions do not match ($2 \neq 3$).
* **Result:** **Undefined**.


* **$AC$**

* **Dimensions:** $(2 \times 3) \times (4 \times 2)$
* **Compatibility:** Inner dimensions do not match ($3 \neq 4$).
* **Result:** **Undefined**.


* **$CA$**

* **Dimensions:** $(4 \times 2) \times (2 \times 3)$
* **Compatibility:** Inner dimensions match ($2 = 2$).
* **Result:** **Defined**, size is **$4 \times 3$**.


* **$AD$**

* **Dimensions:** $(2 \times 3) \times (2 \times 2)$
* **Compatibility:** Inner dimensions do not match ($3 \neq 2$).
* **Result:** **Undefined**.


* **$DA$**

* **Dimensions:** $(2 \times 2) \times (2 \times 3)$
* **Compatibility:** Inner dimensions match ($2 = 2$).
* **Result:** **Defined**, size is **$2 \times 3$**.
