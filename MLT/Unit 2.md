## **1. Linear Regression**

### 🔍 What is it?

Linear Regression ek supervised machine learning algorithm hai jo **continuous output** predict karta hai — jaise ki house price, salary, marks, etc.

Ye basically input (x) aur output (y) ke beech ek **straight line ka relation** dhoondhta hai. Matlab: "Jitna x badhega, utna y badhega ya ghathega."

---

### 🧠 Metaphor:

Sochiye ek painter hai jo **wall ke temperature** ke hisaab se paint ka **dry hone ka time** predict karta hai. Jitni zyada garmi, utni jaldi paint sukh jaayega. To painter ek aisi line draw karta hai jo temperature aur dry time ke beech ka perfect relationship bataye — yeh hi hai linear regression.

---

### 🧾 Formula:

$$
y = mx + c
$$

Machine learning mein ise thoda general bana ke likhte hain:

$$
\hat{y} = w_1x + b
$$

* $\hat{y}$ = predicted output
* $x$ = input feature
* $w_1$ = weight/slope (kitna badlav aayega)
* $b$ = bias/intercept (jab x = 0 ho tab y kya hoga)

---

### ⚙️ Learning Kaise Hota Hai?

Model training ke time par ye model **error** minimize karta hai — jise bolte hain **Loss Function**.

Common loss function:

$$
MSE = \frac{1}{n} \sum_{i=1}^n (y_i - \hat{y}_i)^2
$$

Matlab: Actual value aur predicted value ka difference square kar ke average le lo. Isse model ko pata chalta hai ki usne kitna galat predict kiya hai.

---

### ✅ Example:

Man lijiye hum student ke study hours se marks predict karna chahte hain:

$$
\hat{y} = 10x + 5
$$

Agar ek student 4 ghante padhta hai:

$$
\hat{y} = 10(4) + 5 = 40 + 5 = 45
$$

To model bolta hai: **"Is student ke 45 marks aayenge."**

---

## **2. Logistic Regression**

### 🔍 What is it?

Logistic Regression bhi supervised learning algorithm hai, lekin yeh **classification** ke liye use hoti hai. Jab output **discrete** ho (Yes/No, 0/1, Male/Female), tab Logistic Regression use ki jaati hai.

---

### 🧠 Metaphor:

Sochiye ek **doctor** patient ke symptoms ke base pe decide karna chahta hai ki patient ko **flu hai ya nahi**. Isme result ya to **Yes hoga ya No**. Doctor patient ka data dekhega — jaise body temp, cough, headache — aur fir predict karega: "Flu hai ya nahi?"

Yahan **yes/no decision linearly nahi ho sakta**, isliye logistic regression ek **sigmoid curve** ka use karti hai — jo output ko 0 aur 1 ke beech constrain karti hai.

---

### 📈 Sigmoid Function:

$$
\sigma(z) = \frac{1}{1 + e^{-z}}
$$

Jahan:

* $z = w_1x + b$
* Sigmoid function value hamesha **0 aur 1 ke beech** hoti hai

Ye function predict karta hai ki kisi input ke liye probability kya hai ki output 1 ho (ya Yes ho).

---

### ✅ Example:

Agar $z = 2$, to:

$$
\sigma(2) = \frac{1}{1 + e^{-2}} \approx 0.88
$$

Yani 88% chance hai ki patient ko flu hai.

Agar humne threshold 0.5 set kiya hai, to:

* Agar output > 0.5: Predict **Yes**
* Agar output <= 0.5: Predict **No**

---

### 🧾 Loss Function (Binary Cross Entropy):

$$
Loss = -[y \log(\hat{y}) + (1 - y) \log(1 - \hat{y})]
$$

Ye function ensure karta hai ki agar predicted probability actual se door hai to zyada punishment mile model ko.

---

## **3. Bias Theorem**

### 🔍 What is it?

Bias theorem ek theoretical concept hai jo batata hai ki machine learning model ke **performance** ko 3 major components mein tod sakte hain:

$$
\text{Total Error} = \text{Bias}^2 + \text{Variance} + \text{Irreducible Error}
$$

---

### 🧠 Metaphor:

Sochiye aap **arrow shooting** kar rahe ho:

* **High bias**: Saare arrows target ke bahar ek hi jagah jaa rahe hain (model oversimplified hai — like underfitting)
* **High variance**: Arrows target ke aaspaas random jagah gir rahe hain (model overfitting kar raha hai)
* **Ideal**: Arrows target ke beech gir rahe hain — low bias and low variance.

---

### 🧾 Definitions:

* **Bias**: Kitna aapka model actual values se door hai, on average.
* **Variance**: Kitna aapka model training data ke chhoti chhoti changes par bhi drastically change karta hai.
* **Irreducible Error**: Jo noise ya randomness actual data mein hoti hai — ise hata nahi sakte.

---

### ✅ Example:

Agar aap ek bahut hi simple model se house price predict karne ki koshish kar rahe ho (e.g., sirf area ke basis pe), to model **high bias** dikhayega. Agar aap har chhoti feature ko include kar rahe ho, to model overfit hoke **high variance** dikhaayega.

---

## **4. Naïve Bayes Theorem**

> Aapne shayad “Naïve Bias Theorem” likha tha, lekin machine learning mein iska correct naam hai: **Naïve Bayes Theorem**.

### 🔍 What is it?

Naïve Bayes ek classification algorithm hai jo **Bayes’ Theorem** par based hai. Iska assumption hai ki **features independent hote hain** — isliye iska naam “naïve” (bhola) rakha gaya hai.

---

### 🧠 Metaphor:

Sochiye aap ek **email filter** bana rahe ho jo bataye ki email spam hai ya nahi. Agar kisi email mein “lottery”, “prize”, aur “free” jaise shabd aayein to aapka model kahe: “Bhai ye to spam hi hoga!”

---

### 📘 Bayes’ Theorem:

$$
P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}
$$

Yahan:

* $P(A|B)$: Probability ki event A ho chuki hai given ki B hua hai
* $P(B|A)$: Probability ki B hoga agar A ho
* $P(A)$: Probability ki A ho
* $P(B)$: Probability ki B ho

---

### ✅ Example:

Agar 90% spam emails mein “win” word aata hai, aur koi email mein “win” likha hua hai, to model calculate karega:

**"Is email ke spam hone ki kya probability hai?"**

Model different words ki frequencies dekhta hai aur final probability ke base par decide karta hai — Spam ya Not Spam.

---

