# javascript-number-methods
Bu belge Javascript number tiplerinin ve Math fonksiyonlarının temel metotlarını içeren Türkçe belge niteliğinde hazırlanmış notlardan oluşur. Metotlar, tanımları ve kullanım örneklerinden oluşur. Hazırlayan @burakkrt 

# Number Methods

### Number(), + , parseInt(), parseFloat()

```jsx
Console.log(Number("123")); // return 123 (convert string to number)
console.log(+"123");  // return 123 (convert string to number)
console.log(parseInt("123")); // return 123 (convert string to number)

// (float değer Integer 'a dönüştüğünde küsüratli değer kabul edilmez.)
console.log(parseInt("12.34")); // return 12
console.log(parseFloat("12.34")); // return 12.34 (convert string to number)
```

### toString()

```jsx
const nbr = 15
console.log(nbr.toString()) // return 15
```

### toFixed()

bir sayının ondalık basamaklarını belirtilen sayıda kesirli basamağa yuvarlar ve sonuç olarak bir dize (`string`) döndürür.

```jsx
const n1 = 214.45
console.log(n1.toFixed(1));// "214.4"
console.log(n1.toFixed(4));// "214.4500"  (kalan fazlalıkları 0 olarak işler)
console.log(+n1.toFixed(4));// 214.4500  (convert string to number)
```

### toPrecision()

Bir sayıyı belirli bir hassasiyetle (belirli toplam basamak sayısıyla) biçimlendirmek için kullanılır. Bu metot, sayının tam kısmını ve ondalık kısmının belirtilen toplam basamak sayısına kadar kesirli basamaklarını içerecek şekilde biçimlendirir.

```jsx
let num = 3.14159;
let formattedNum = num.toPrecision(4); // '3.142'

let integerNum = 42;
let formattedInt = integerNum.toPrecision(4); // '42.00'
```

### toLocaleString()

Bir sayıyı veya tarihi, belirli bir dil ve bölgeye özgü biçimlendirmeye göre bir dizeye dönüştürmek için kullanılır. Bu, sayıları veya tarihleri kullanıcının yerel dil ve bölgeye göre anlamasını kolaylaştırmak için kullanışlıdır. `string` döndürür.

```jsx
const n1 = 1800000;

// Tarayıcının diline göre otomatik ülke formatı seçer (burada tr)
console.log(n1.toLocaleString(());// return "1.800.000"
//istersek kendimiz belirtebiliriz.
console.log(n1.toLocaleString(("tr-TR"));// return "1.800.000"
```

### Number.isInteger()

Belirtilen bir sayının integer (tam sayı) olup olmadığını kontrol eder ve geriye boolean değer döndürür.

```jsx
console.log(Number.isInteger(24)); // true
console.log(Number.isInteger(24.00)); // true
console.log(Number.isInteger(24.04)); // false
console.log(Number.isInteger([1,2,3])); // false
console.log(Number.isInteger("24")); // false
```

### All Math Functions

### Math.abs()

Bir sayının mutlak değerini alır. Negatif değerleri pozitife çevirmek için kullanabiliriz.

```jsx
console.log(Math.abs(5)); // 5 - Pozitif değerin mutlak değeri kendisidir.
console.log(Math.abs(-5)); // 5 - Negatif değerin mutlak değeri pozitif hâlidir.
console.log(Math.abs(0)); // 0 - Sıfırın mutlak değeri kendisi 0'dır.
console.log(Math.abs(-3.14)); // 3.14 - Negatif değerin mutlak değeri pozitif hâlidir.
console.log(Math.abs("42")); // 42 - "42" ifadesi sayıya çevrilebilir ve mutlak değeri kendisi 42'dir.
console.log(Math.abs("Hello")); // NaN - "Hello" ifadesi sayıya çevrilemez, bu nedenle mutlak değeri NaN'dir.
```

### Math.ceil()

Bir sayıyı her zaman yukarıya yuvarlar.

```jsx
console.log(Math.ceil(0.95)); // Expected output: 1
console.log(Math.ceil(4)); // Expected output: 4
console.log(Math.ceil(7.004)); // Expected output: 8
console.log(Math.ceil(-7.004)); // Expected output: -7
```

### Math.floor()

Bir sayıyı her zaman aşağıya yuvarlar.

```jsx
console.log(Math.floor(5.95));// Expected output: 5
console.log(Math.floor(5.05));// Expected output: 5
console.log(Math.floor(5));// Expected output: 5
console.log(Math.floor(-5.05));// Expected output: -6
```

### Math.max()

Belirtilen bir veya daha fazla sayı arasında en büyük değeri döndürmek için kullanılır.

```jsx
console.log(Math.max(5, 10, 15, 20)); // 20 - En büyük sayı 20'dir.
console.log(Math.max(-5, 3, -10, 8)); // 8 - En büyük sayı 8'dir.
console.log(Math.max(0, 0, 0, 0)); // 0 - Tüm sayılar 0 olduğunda en büyük sayı yine 0'dır.
console.log(Math.max(3.14, 2.71, 1.618)); // 3.14 - En büyük sayı 3.14'dür.
console.log(Math.max("42", "100", "7")); // 100 - "42", "100" ve "7" sayıya çevrilebilir ve en büyük sayı 100'dür.
console.log(Math.max(10, "Hello", -8)); // 10 - "Hello" sayıya çevrilemez, bu nedenle hesaplamada göz ardı edilir.
console.log(Math.max()); // -Infinity - Hiç sayısal argüman yok, bu nedenle -Infinity döndürülür.
```

### Math.max()

Belirtilen bir veya daha fazla sayı arasında en küçük değeri döndürmek için kullanılır.

```jsx
console.log(Math.min(5, 10, 15, 20)); // 5 - En küçük sayı 5'tir.
console.log(Math.min(-5, 3, -10, 8)); // -10 - En küçük sayı -10'dur.
console.log(Math.min(0, 0, 0, 0)); // 0 - Tüm sayılar 0 olduğunda en küçük sayı yine 0'dır.
console.log(Math.min(3.14, 2.71, 1.618)); // 1.618 - En küçük sayı 1.618'dir.
console.log(Math.min("42", "100", "7")); // 7 - "42", "100" ve "7" sayıya çevrilebilir ve en küçük sayı 7'dir.
console.log(Math.min(10, "Hello", -8)); // -8 - "Hello" sayıya çevrilemez, bu nedenle hesaplamada göz ardı edilir.
console.log(Math.min()); // Infinity - Hiç sayısal argüman yok, bu nedenle Infinity döndürülür.
```

### Math.pow()

Bir sayının üssünü hesaplamak için kullanılır. `Math.pow(temelDeğer, üssü)`

```jsx
console.log(Math.pow(2, 3)); // 8 - 2^3 = 2 * 2 * 2 = 8
console.log(Math.pow(5, 2)); // 25 - 5^2 = 5 * 5 = 25
console.log(Math.pow(10, 0)); // 1 - Herhangi bir sayının 0. üssü her zaman 1'dir.
console.log(Math.pow(3, -2)); // 0.1111111111111111 - 3^(-2) = 1 / (3^2) = 1 / 9 = 0.1111111111111111
console.log(Math.pow(4, 0.5)); // 2 - 4^(0.5) = Karekök(4) = 2
```

### Math.random()

0 (dahil) ile 1 (hariç) arasında rastgele bir ondalık sayı üretmek için kullanılır.

```jsx
const randomNumber = Math.random();
console.log(randomNumber); // Örneğin, 0.7267456282563128

// 0 ile 10 arasında rastgele bir sayı üretmek için:
const randomBetween0And10 = Math.random() * 10;
console.log(randomBetween0And10); // Örneğin, 7.267456282563128

// 1 ile 100 arasında rastgele bir tam sayı üretmek için:
const randomIntBetween1And100 = Math.floor(Math.random() * 100) + 1;
console.log(randomIntBetween1And100); // Örneğin, 42
```

### **Math.round()**

Bir ondalık sayıyı en yakın tam sayıya yuvarlamak için kullanılır.

```jsx
console.log(Math.round(3.2)); // 3 - 3.2 ondalık kısmı 0.5'ten küçük olduğu için 3'e yuvarlanır.
console.log(Math.round(6.8)); // 7 - 6.8 ondalık kısmı 0.5'ten büyük olduğu için 7'ye yuvarlanır.
console.log(Math.round(1.5)); // 2 - 1.5 ondalık kısmı 0.5 olduğu için yukarıya yuvarlanır.
console.log(Math.round(2.4)); // 2 - 2.4 ondalık kısmı 0.5'ten küçük olduğu için 2'ye yuvarlanır.
console.log(Math.round(-3.7)); // -4 - -3.7 ondalık kısmı 0.5'ten küçük olduğu için -4'e yuvarlanır.
```

### Math.sing()

Bir sayının negatif, pozitif veya nötr olup olmadığına göre 0,1,-1 değerlerini döndürür.

- Eğer **`x`** pozitifse, sonuç **`1`** olur.
- Eğer **`x`** negatifse, sonuç `-1` olur.
- Eğer **`x`** sıfıra eşitse, sonuç **`0`** olur.

```jsx
console.log(Math.sign(5)); // 1 - Pozitif sayının işareti 1'dir.
console.log(Math.sign(-5)); // -1 - Negatif sayının işareti -1'dir.
console.log(Math.sign(0)); // 0 - Sıfırın işareti 0'dır.
console.log(Math.sign("42")); // 1 - "42" ifadesi sayıya çevrilebilir ve pozitif sayının işareti 1'dir.
console.log(Math.sign("-3.14")); // -1 - "-3.14" ifadesi sayıya çevrilebilir ve negatif sayının işareti -1'dir.
console.log(Math.sign("Hello")); // NaN - "Hello" ifadesi sayıya çevrilemez, bu nedenle sonuç NaN'dir.
```
