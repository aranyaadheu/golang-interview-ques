# Golang Interview Questions and Answers (BASIC)

## কন্টেন্ট সূচি

## কন্টেন্ট সূচি

| #  | প্রশ্ন | উদাহরণ |
|----|------------------------------------------------------|------------|
| ১  | [What is scope?](#১-what-is-scope)                 | [উদাহরণ](#উদাহরণ) |
| ২  | [What is block?](#২-what-is-block)                 | [উদাহরণ: (Nested Block Scope)](#উদাহরণ-nested-block-scope) |
| ৩  | [How many types of scopes are there in Golang?](#৩-how-many-types-of-scopes-are-there-available-on-golang) | |
| ৪  | [What is the standard or named function?](#৪-what-is-the-standard-or-named-function) | [উদাহরণ](#উদাহরণ-1) |
| ৫  | [What is anonymous function?](#৫-what-is-anonymous-function) | [উদাহরণ](#উদাহরণ-2) |
| ৬  | [What is expression?](#৬-what-is-expression)       | [উদাহরণ](#উদাহরণ-3) |
| ৭  | [What is function expression?](#৭-what-is-function-expression) | [উদাহরণ](#উদাহরণ-4) |
| ৮  | [What is immediately invoked function expression (IIFE)?](#৮-what-is-immediately-invoked-function-expression-iife) | [উদাহরণ](#উদাহরণ-5) |
| ৯  | [Difference between arguments and parameters](#৯-difference-between-arguments-and-parameters) | [উদাহরণ](#উদাহরণ-6) |
| ১০ | [What is first-class function or higher-order function?](#১০-what-is-first-class-function-or-higher-order-function) | [উদাহরণ](#উদাহরণ-7) |
| ১১ | [Difference between first-order function and higher-order function](#১১-difference-between-first-order-function-and-higher-order-function) | |
| ১২ | [Difference between first-order logic and higher-order logic](#১২-difference-between-first-order-logic-and-higher-order-logic) | |
| ১৩ | [What is callback function?](#১৩-what-is-callback-function) | [উদাহরণ](#উদাহরণ-8) |
| ১৪ | [What is the first-class citizen?](#১৪-what-is-the-first-class-citizen) | |
| ১৫ | [What is init function?](#১৫-what-is-init-function) | [উদাহরণ](#উদাহরণ-9) |
| ১৬ | [Difference between compile time and run time](#১৬-difference-between-compile-time-and-run-time) | [কম্পাইল টাইম](#কম্পাইল-টাইম-compile-time), [রান টাইম](#রান-টাইম-run-time) |
| ১৭ | [What is escape analysis?](#১৭-what-is-escape-analysis) | [উদাহরণ](#উদাহরণ-10) |
| ১৮ | [Describe 2 phases of running a Go program](#১৮-describe-2-phases-of-running-a-go-program) | [উদাহরণ](#উদাহরণ-11) |
| ১৯ | [What is closure in Go?](#১৯-what-is-closure-in-go) | [উদাহরণ](#উদাহরণ-12) |
| ২০ | [What is struct in Go?](#২০-what-is-struct-in-go) | [উদাহরণ](#উদাহরণ-13) |
| ২১ | [What is an instance?](#২১-what-is-an-instance) | [উদাহরণ](#উদাহরণ-14) |
| ২২ | [What are member variables?](#২২-what-are-member-variables) | [উদাহরণ](#উদাহরণ-15) |
| ২৩ | [What is instantiation?](#২৩-what-is-instantiation) | [উদাহরণ](#উদাহরণ-16) |
| ২৪ | [What is the receiver function?](#২৪-what-is-the-receiver-function) | [উদাহরণ](#উদাহরণ-17) |
| ২৫ | [Difference between expression and statement](#২৫-difference-between-expression-and-statement) | [উদাহরণ](#উদাহরণ-18), [পার্থক্য সংক্ষেপে](#পার্থক্য-সংক্ষেপে) |
| ২৬ | [What is pointer? And difference between pass by value vs pass by reference](#২৬-what-is-pointer-and-difference-between-pass-by-value-vs-pass-by-reference) | [উদাহরণ](#উদাহরণ-19) |
| ২৭ | [Difference between pass by value vs pass by reference](#২৭-difference-between-pass-by-value-vs-pass-by-reference) | [উদাহরণ](#উদাহরণ-20), [উদাহরণ](#উদাহরণ-21), [পার্থক্য সংক্ষেপে](#পার্থক্য-সংক্ষেপে-1) |

## ১। What is scope?

স্কোপ হলো একটি নির্দিষ্ট অংশ যেখানে কোনো ভেরিয়েবল বা ফাংশনকে অ্যাক্সেস বা ব্যবহার করা যায়।

**Types of Scope:**

**লোকাল স্কোপ (Local Scope):**
যদি কোনো ভেরিয়েবল বা ফাংশন শুধুমাত্র একটি নির্দিষ্ট ব্লক (যেমন: ফাংশন, লুপ, অথবা কন্ডিশনাল স্টেটমেন্ট ( if else, switch ) এর ভিতরে ডিক্লেয়ার করা হয়, তাহলে তা ঐ ব্লকের বাইরে অ্যাক্সেস করা যায় না। এটাকেই লোকাল স্কোপ বলে।

**গ্লোবাল স্কোপ (Global Scope):**
যদি কোনো ভেরিয়েবল বা ফাংশন প্যাকেজ লেভেলে ডিক্লেয়ার করা হয়, তাহলে তা পুরো প্রোগ্রামের মধ্যে অ্যাক্সেসযোগ্য হয়। এটাকে গ্লোবাল স্কোপ বলে।

### উদাহরণ

```go
package main
import "fmt"

// গ্লোবাল ভেরিয়েবল
var globalVar = "আমি গ্লোবাল ভেরিয়েবল"

func main() {
   // লোকাল ভেরিয়েবল
   localVar := "আমি লোকাল ভেরিয়েবল"
   fmt.Println(globalVar) // গ্লোবাল ভেরিয়েবল অ্যাক্সেস করা যায়
   fmt.Println(localVar)  // লোকাল ভেরিয়েবল অ্যাক্সেস করা যায়
}

func anotherFunction() {
   fmt.Println(globalVar) // গ্লোবাল ভেরিয়েবল অ্যাক্সেস করা যায়
   // fmt.Println(localVar) // এটা কাজ করবে না, কারণ localVar লোকাল স্কোপে   আছে
}
```

---

## ২। What is block?

Block বলতে একটি নির্দিষ্ট অঞ্চল বা সীমানা বোঝায়, যা `{}` দ্বারা আবদ্ধ থাকে। এই ব্লকের মধ্যে যেকোনো কোড লেখা হয় এবং তা একটি নির্দিষ্ট স্কোপ (Scope) তৈরি করে। ব্লকের ভিতরে ডিক্লেয়ার করা ভেরিয়েবল বা ফাংশন শুধুমাত্র ঐ ব্লকের মধ্যেই অ্যাক্সেসযোগ্য হয়।

### উদাহরণ: (Nested Block Scope)

```go
func nestedBlockExample() {
   a := 5
   {
       b := 10 // এই ভেরিয়েবল b শুধুমাত্র এই নেস্টেড ব্লকের ভিতরে অ্যাক্সেসযোগ্য
       fmt.Println(a + b)
   }
   // fmt.Println(b) // এটি কাজ করবে না, কারণ b এর স্কোপ নেস্টেড ব্লকের বাইরে নেই
}
```

---

## ৩। How many types of scopes are there available on Golang?

1. **Global scope** - পুরো প্রোগ্রামে অ্যাক্সেসযোগ্য।
2. **Local scope** - শুধুমাত্র নির্দিষ্ট ব্লকের ভিতরে অ্যাক্সেসযোগ্য।
3. **Package scope** - প্যাকেজের বাইরে থাকা ভেরিয়েবল ও ফাংশন একই প্যাকেজের অন্য ফাইলেও ব্যবহার করা যায়।

---

## ৪। What is the standard or named function?

Standard বা Named Function হলো এমন একটি ফাংশন যার একটি নির্দিষ্ট নাম থাকে। ফাংশন কল করার জন্য এই নামটি ব্যবহার করা হয়।

### উদাহরণ

```go
package main
import "fmt"

// একটি নেমড ফাংশন যা দুটি সংখ্যার যোগফল রিটার্ন করে
func addNumbers(a int, b int) int {
   return a + b
}

func main() {
  // ফাংশনটি কল করা হচ্ছে
   result := addNumbers(5, 7)
   fmt.Println("যোগফল:", result) // আউটপুট: যোগফল: 12
}
```

```
- addNumbers হলো একটি standard or Named Function ফাংশন।
- এটি দুটি প্যারামিটার (a এবং b) গ্রহণ করে এবং তাদের যোগফল রিটার্ন করে।
- main ফাংশন থেকে addNumbers ফাংশনটি কল করা হয়েছে।

```

---

## ৫। What is anonymous function?

Anonymous Function বলতে এমন ফাংশনকে বোঝায় যার কোনো নাম থাকে না। এই ফাংশনগুলো সাধারণত তখনই ব্যবহার করা হয় যখন আমাদের ফাংশনটি শুধুমাত্র একটি নির্দিষ্ট জায়গায় ব্যবহার করার প্রয়োজন হয়, এবং এটিকে পুনরায় ব্যবহার করার দরকার হয় না।

### উদাহরণ

```go
package main
import "fmt"

func main() {
   // একটি এননিমাস ফাংশন ডিক্লেয়ার এবং কল করা
   func() {
       fmt.Println("এটি একটি এননিমাস ফাংশন")
   }()
}
```

---

## ৬। What is expression?

Expression হলো প্রোগ্রামিং-এ এমন একটি কোডের অংশ যা কোনো নির্দিষ্ট মান (value) তৈরি করে। অন্য কথায়, যখন কোনো কোড একটি ফলাফল বা আউটপুট দেয়, তখন সেই কোডকে এক্সপ্রেশন বলা হয়।

### উদাহরণ

```go
- result := 2 + 3 // এটি একটি গাণিতিক এক্সপ্রেশন
- isTrue := (5 > 3) && (10 < 20) // এটি একটি লজিক্যাল এক্সপ্রেশন
- func add(a int, b int) int {
   return a + b
}
result := add(4, 6) // এটি একটি ফাংশন কল এক্সপ্রেশন
- if (x > 10) { ... }  // এটি একটি কন্ডিশনাল এক্সপ্রেশন
```

---

## ৭। What is function expression?

ফাংশন এক্সপ্রেশন (Function Expression) বলতে এমন একটি ফাংশনকে বোঝায় যা একটি ভেরিয়েবলের মধ্যে স্টোর করা হয়।

### উদাহরণ

```go
package main
import "fmt"
func main() {
   // একটি ফাংশন এক্সপ্রেশন তৈরি করা হচ্ছে
   add := func(a int, b int) int {
       return a + b
   }
   // ফাংশনটি কল করা হচ্ছে
   result := add(5, 7)
   fmt.Println("যোগফল:", result) // আউটপুট: যোগফল: 12
}
```

---

## ৮। What is immediately invoked function expression (IIFE)?

IIFE - Immediately Invoked Function Expression বলতে এমন একটি ফাংশনকে বোঝায় যা ডিক্লেয়ার করার সাথে সাথে তৎক্ষণাৎ কল করা হয়। অন্য কথায়, এটি একটি ফাংশন যা প্রোগ্রামে লেখার সময়ই এক্সিকিউট হয়ে যায়। এই ফাংশনটি শুধুমাত্র একবার ব্যবহার করা হয়, এবং পরে এটি পুনরায় কল করা যায় না।

### উদাহরণ

```go
package main
import "fmt"
func main() {
   // একটি IIFE তৈরি এবং তৎক্ষণাৎ কল করা হচ্ছে
   func() {
       fmt.Println("এটি একটি IIFE")
   }() // ফাংশনটি ডিক্লেয়ার করার সাথে সাথে কল করা হচ্ছে
}
```

---

## ৯। Difference between arguments and parameters

**Parameter:** প্যারামিটার হল ফাংশন ডিফাইন করার সময় যে ভেরিয়েবলগুলো ব্যবহার করা হয়। এগুলো মূলত ফাংশনের জন্য একটা প্লেসহোল্ডার হিসেবে কাজ করে।
**Argument:** আর্গুমেন্ট হল ফাংশন কল করার সময় যে ডাটাগুলি পাস করা হয়। পাস করা ডাটাগুলি প্যারামিটারে অ্যাসাইন হয়ে ফাংশনের কাজ চালায়।

### উদাহরণ

```go
func add(a, b int) int { // a এবং b হল প্যারামিটার
   return a + b
}

result := add(3, 5)  // 3 এবং 5 হল আর্গুমেন্ট
```

---

## ১০। What is first-class function or higher-order function?

Higher-order function বলতে এমন ফাংশনকে বোঝায় যা অন্য ভেরিয়েবলের মতোই ব্যবহার করা যায়। অন্য কথায় ফাংশনটি একটি ভেরিয়েবলে স্টোর করা যায়, যে ফাংশন প্যারামিটারের ইনপুট হিসেবে আরেকটা ফানশনকে রিসিভ করতে পারে এবং অন্য ফাংশন থেকে রিটার্ন করা যায়।

**Why we call Higher Order Function >< First class function**
যেহুতু higher order function আরেকটা ফাংশনকে রিসিভ করতে পারে & ফাংশনটি একটি ভেরিয়েবলে স্টোর করা যায় as like first class citizen তাই higher order function কে first class function বলা হয়।

### উদাহরণ

```go
// 1. ফাংশনকে প্যারামিটার হিসেবে গ্রহণ করা:

func applyOperation(a int, b int, operation func(int, int) int) int {
   return operation(a, b)
}
func main() {
   add := func(x int, y int) int {
       return x + y
   }
   result := applyOperation(10, 5, add)
   fmt.Println(result) // আউটপুট: 15
}

// 2. ফাংশনকে রিটার্ন করা:

func createGreeter(greeting string) func(string) string {
   return func(name string) string {
       return greeting + ", " + name + "!"
   }
}
func main() {
   greetInEnglish := createGreeter("Hello")
   greetInBangla := createGreeter("হ্যালো")


   fmt.Println(greetInEnglish("John")) // আউটপুট: Hello, John!
   fmt.Println(greetInBangla("রহিম")) // আউটপুট: হ্যালো, রহিম!
}

```

---

## ১১। Difference between first-order function and higher-order function

**First-Order Function:**
ফার্স্ট অর্ডার ফাংশন হলো এমন ফাংশন যা অন্য কোনো ফাংশনকে প্যারামিটার হিসেবে গ্রহণ করে না এবং অন্য কোনো ফাংশনকে রিটার্নও করে না। এটি শুধুমাত্র নরমাল ডেটা (যেমন: সংখ্যা, স্ট্রিং, অ্যারে ইত্যাদি) নিয়ে কাজ করে।

**Higher-Order Function:**
হাইয়ার অর্ডার ফাংশন হলো এমন ফাংশন যা অন্য ফাংশনকে প্যারামিটার হিসেবে গ্রহণ করে অথবা অন্য ফাংশনকে রিটার্ন করে। এটি ফাংশনের উপর কাজ করে এবং ফাংশনকে ডেটা হিসেবে ব্যবহার করে।

---

## ১২। Difference between first order logic and higher order logic

**First Order Logic:**
First-Order Logic হলো এমন একটি লজিক সিস্টেম যা শুধুমাত্র Object, Property, Relation নিয়ে কাজ করে।

**Higher-Order Logic:**
Higher-Order Logic এমন একটি লজিক সিস্টেম যা Object, Property, Relation নিয়ে ত কাজ করেই এবং পাশাপাশি Rule নিয়েও কাজ করে।

**সহজ কথায়:**
ফার্স্ট-অর্ডার লজিক: এখানে আমরা শুধু "জিনিস" (অবজেক্ট) নিয়ে কথা বলি। যেমন, "সব ফল মিষ্টি"। এটি সাধারণ এবং সীমিত।
হায়ার-অর্ডার লজিক: এখানে আমরা "জিনিস" ছাড়াও "বৈশিষ্ট্য" বা "পদ্ধতি" নিয়ে কথা বলতে পারি। যেমন, "কিছু বৈশিষ্ট্য আছে যা সব ফলের জন্য সত্য"। এটি আরও শক্তিশালী।

**বিঃদ্রঃ** GO প্রোগ্রামিং-এ, ফার্স্ট-অর্ডার লজিক হলো সাধারণ ফাংশন যেগুলো শুধু ডেটা নিয়ে কাজ করে। আর হায়ার-অর্ডার লজিক হলো ফাংশন যেগুলো অন্য ফাংশন নিয়ে কাজ করে।

## ১৩। What is callback function?

Callback Function হলো এমন একটি ফাংশন যা অন্য একটি ফাংশনের ভিতরে প্যারামিটার হিসেবে পাঠানো হয় এবং প্রথম ফাংশনটি যখন প্রয়োজন হয়, তখন এই কলব্যাক ফাংশনটিকে কল করে। অন্য কথায়, কলব্যাক ফাংশন হলো এমন একটি ফাংশন যা অন্য ফাংশনের দ্বারা "কল করার" জন্য পাঠানো হয়।

### উদাহরণ

```go
// একটি ফাংশন যা কলব্যাক ফাংশন গ্রহণ করে
func calculate(a int, b int, operation func(int, int) int) int {
   return operation(a, b)
}

func main() {
   // কলব্যাক ফাংশন হিসেবে add ফাংশন ব্যবহার করা হচ্ছে
   add := func(x int, y int) int {
       return x + y
   }

   // কলব্যাক ফাংশন হিসেবে subtract ফাংশন ব্যবহার করা হচ্ছে
   subtract := func(x int, y int) int {
       return x - y
   }


   result1 := calculate(10, 5, add)
   result2 := calculate(10, 5, subtract)


   fmt.Println("যোগফল:", result1)       // আউটপুট: 15
   fmt.Println("বিয়োগফল:", result2)     // আউটপুট: 5
}

```

---

### ১৪। What is the first-class citizen?

First-Class Citizen বলতে বোঝায় যা প্রোগ্রামের মধ্যে অন্য যেকোনো ডেটা টাইপের মতোই ব্যবহার করা যায়। GO-তে ফাংশন হলো ফার্স্ট ক্লাস সিটিজেন, কারণ ফাংশনকে ভেরিয়েবলে স্টোর করা, প্যারামিটার হিসেবে পাঠানো, অথবা অন্য ফাংশন থেকে রিটার্ন করা যায়।

---

### ১৫। What is init function?

**init ফাংশন** হলো একটি বিশেষ ফাংশন যা কোনো প্যাকেজ বা ফাইল লোড হওয়ার সময় অটোমেটিকভাবে একবার কল হয়। এটি প্রোগ্রামের প্রাথমিক সেটআপ বা ইনিশিয়ালাইজেশন কাজে ব্যবহৃত হয়, যেমন: ভেরিয়েবল ইনিশিয়ালাইজ করা, ডাটাবেস কানেকশন তৈরি করা, কনফিগারেশন লোড করা ইত্যাদি।

#### উদাহরণ

```go
// package.go
package mypackage
import "fmt"

func init() {
   fmt.Println("Init from mypackage")
}

// main.go
package main
import (
   "fmt"
   "mypackage"
)

func main() {
   fmt.Println("Main function")
}
```

**আউটপুট:**

```
Init from mypackage
Main function
```

---

### ১৬। Difference between compile time and run time

#### **কম্পাইল টাইম (Compile Time):**

- কম্পাইল টাইম হলো যখন প্রোগ্রামটি কম্পাইলার দ্বারা কম্পাইল করা হয়। এই সময়ে কম্পাইলার প্রোগ্রামের সোর্স কোডকে মেশিন কোডে (বাইনারি কোড) রূপান্তর করে।

- এই ধাপে কোডের সিনট্যাক্স (যেমন: একটি সেমিকোলন ; মিস করেন) এবং কিছু লজিক্যাল ভুল ধরা পড়ে। যদি কোডে কোনো ভুল থাকে, তবে কম্পাইলার সেটি চিহ্নিত করে এবং প্রোগ্রামটি run হবার আগেই প্রোগ্রামারকে জানিয়ে দেয়।

**উদাহরণ:** ধরা যাক, আপনি একটি প্রোগ্রামে একটি ভেরিয়েবল ব্যবহার করেছেন কিন্তু সেটি ডিক্লেয়ার করেননি। এই ভুলটি কম্পাইল টাইমে ধরা পড়বে, এবং কম্পাইলার একটি এরর মেসেজ দেখাবে, যেমন "undefined variable"।

#### **রান টাইম (Run Time):**

- রান টাইম হলো যখন প্রোগ্রামটি চালু অবস্থায় থাকে এবং এক্সিকিউট হয়। এই সময়ে প্রোগ্রামটি ব্যবহারকারীর ইনপুট নেয়, ডেটা প্রসেস করে এবং আউটপুট দেয়।

- এই ধাপে প্রোগ্রামটি ইনপুট নেয়, সেই ইনপুট প্রসেস করে, এবং আউটপুট দেয়। রান টাইমে কিছু ভুল ধরা পড়তে পারে যা কম্পাইল টাইমে ধরা পড়েনি, যেমন লজিক্যাল ভুল বা রানটাইম এরর (যেমন শূন্য দিয়ে ভাগ করা)।

**উদাহরণ:** ধরা যাক, আপনার প্রোগ্রামে একটি লুপ আছে যা কোনো শর্তের কারণে চিরতরে চলতে থাকে (ইনফিনিট লুপ)। এই ভুলটি কম্পাইল টাইমে ধরা পড়বে না, কিন্তু যখন প্রোগ্রামটি চালানো হবে, তখন এটি রান টাইমে সমস্যা সৃষ্টি করবে।

---

### ১৭। What is escape analysis?

Escape Analysis হলো গো (Go) প্রোগ্রামিং-এর একটি অপটিমাইজেশন টুল বা প্রক্রিয়া, যা কম্পাইলার দ্বারা ব্যবহৃত হয়। এটি ডিসাইড করে যে কোনো ভেরিয়েবল বা ডেটা ফাংশনের বাইরে ব্যবহার হতে পারে কিনা । এই বিশ্লেষণের উপর ভিত্তি করে কম্পাইলার ডিসাইড করে যে ভেরিয়েবলটি মেমোরির স্ট্যাক (Stack) নাকি হিপ (Heap) - এ store করা হবে।

#### উদাহরণ

```go
func createPointer() *int {
   x := 42 // x একটি ভেরিয়েবল
   return &x // x-এর পয়েন্টার রিটার্ন করা হচ্ছে
}

func main() {
   p := createPointer()
   fmt.Println(*p)
}
fmt.Println(*p)
}
```

```
এখানে x ভেরিয়েবলটি createPointer ফাংশনের ভিতরে তৈরি হয়েছে, কিন্তু এর পয়েন্টার ফাংশনের বাইরে রিটার্ন করা হয়েছে।
তাই x ফাংশনের বাইরে ব্যবহার হতে পারে।
এটি ফাংশন শেষ হওয়ার পরেও বিদ্যমান থাকতে হবে। তাই কম্পাইলার x-কে হিপ মেমোরি -তে store করবে।
```

---

### ১৮। Describe 2 phases of running a Go program

**১। In the Compilation Phase:** এই Phase এ GO কম্পাইলার সোর্স কোডকে মেশিন কোডে (Executable Binary Code) রূপান্তর করে ও সিনট্যাক্স এবং টাইপ চেকিং করে।

**২। In the Execution Phase:** এই Phase এ compiled binary code system এ run হয় এবং executing the program's logic.

#### উদাহরণ

```bash
go build main.go  # Compilation Phase (creates an executable)
./main            # Execution Phase (runs the program)
```

---

### ১৯। What is closure in Go?

ক্লোজার(closure) হলো এমন একটি ফাংশন যা তার নিজের স্কোপের বাইরের ভেরিয়েবলগুলোকে "মনে রাখে" এমনকি বাইরের ফাংশনের execution শেষ হবার পরেও এবং সেগুলোকে ব্যবহার করতে পারে।
উদাহরণ:

#### উদাহরণ

```go
package main
import "fmt"
// একটি ফাংশন যা একটি ক্লোজার রিটার্ন করে
func createCounter() func() int {
   counter := 0
   return func() int {
       counter++
       return counter
   }
}
func main() {

   counter1 := createCounter()
   fmt.Println(counter1()) // আউটপুট: 1
   fmt.Println(counter1()) // আউটপুট: 2

   counter2 := createCounter()
   fmt.Println(counter2()) // আউটপুট: 1
   fmt.Println(counter2()) // আউটপুট: 2
}

```

---

### ২০। What is struct in Go?

**Struct** হলো গো (Go) প্রোগ্রামিং-এর একটি গুরুত্বপূর্ণ ডেটা স্ট্রাকচার। এটি একটি কাস্টম ডেটা টাইপ যা বিভিন্ন ধরনের ডেটা ফিল্ড (ভেরিয়েবল) একত্রে গ্রুপ করে রাখতে ব্যবহৃত হয়। স্ট্রাক্ট ব্যবহার করে আমরা একটি একক ইউনিটে বিভিন্ন ধরনের ডেটা (যেমন: স্ট্রিং, ইন্টিজার, বুলিয়ান ইত্যাদি) সংরক্ষণ করতে পারি।

#### উদাহরণ

```go
package main
import "fmt"

type Person struct {
   Name    string
   Age     int
   Address string
}

func main() {
   p2 := Person{Name: "Alice", Age: 25, Address: "London"}
   fmt.Println("Name:", p2.Name)
   fmt.Println("Age:", p2.Age)
   fmt.Println("Address:", p2.Address)
}
```

---

### ২১। What is an instance?

**Instance** হলো যখন আমরা একটি struct বা কোনো কাস্টম ডেটা টাইপের জন্য একটি ভেরিয়েবল তৈরি করি, তখন সেই ভেরিয়েবলটিকে ওই ডেটা টাইপের একটি ইনস্ট্যান্স বলা হয়।

- ডেটা টাইপ হলো একটি ব্লুপ্রিন্ট বা প্ল্যান (যেমন: struct), এবং ইনস্ট্যান্স হলো সেই প্ল্যান অনুযায়ী তৈরি একটি বাস্তব অবজেক্ট।
- উদাহরণস্বরূপ, যদি আমরা একটি struct ডিক্লেয়ার করি যা "ব্যক্তি" (Person) প্রতিনিধিত্ব করে, তাহলে একটি বাস্তব ব্যক্তির ডেটা ধারণ করার জন্য যে ভেরিয়েবলটি তৈরি করা হয়, সেটি হলো একটি ইনস্ট্যান্স।

#### উদাহরণ

```go
package main
import "fmt"
// একটি স্ট্রাক্ট ডিক্লেয়ার করা
type Person struct {
   Name string
   Age  int
}
func main() {
   // স্ট্রাক্টের একটি ইনস্ট্যান্স তৈরি করা
   p1 := Person{Name: "John", Age: 30}
   p2 := Person{Name: "Alice", Age: 25}


   fmt.Println("Person 1:", p1)
   fmt.Println("Person 2:", p2)
}

```

```
ব্যাখ্যা:
Person হলো একটি স্ট্রাক্ট (ব্লুপ্রিন্ট)।
p1 এবং p2 হলো Person স্ট্রাক্টের দুটি ইনস্ট্যান্স।
প্রতিটি ইনস্ট্যান্সের নিজস্ব ডেটা আছে (Name এবং Age)।
```

---

### ২২। What are member variables?

Go প্রোগ্রামিং ভাষায় মেম্বার ভেরিয়েবল হল সেই সকল ভেরিয়েবল যা একটি Struct এর ভিতরে Define করা হয়। এগুলিকে আমরা 'ফিল্ড' (Fields) হিসেবেও উল্লেখ করি।
স্ট্রাক্টের মেম্বার ভেরিয়েবলগুলি যেকোনো ডাটা টাইপের হতে পারে, যেমন:

**প্রাথমিক টাইপ** (int, string, bool)
**জটিল টাইপ** (array, slice, map)

#### উদাহরণ

```go
type কর্মচারী struct {
   আইডি     int
   নাম      string
   বিভাগ   string
   বেতন    float64
   সক্রিয়  bool
   দক্ষতা   []string
}
```

```
 এখানে, কর্মচারী স্ট্রাক্টে নিম্নলিখিত মেম্বার ভেরিয়েবল আছে:
 আইডি: একটি integer ফিল্ড
 নাম: একটি string ফিল্ড
 বিভাগ: একটি string ফিল্ড
 বেতন: একটি floating-point ফিল্ড
 সক্রিয়: একটি boolean ফিল্ড
 দক্ষতা: একটি string slice ফিল্ড

```

---

### ২৩। What is instantiation?

**Instantiation** হলো একটি ডেটা টাইপের জন্য একটি ইনস্ট্যান্স তৈরি করার পদ্ধতি।

- ডেটা টাইপ হলো একটি ব্লুপ্রিন্ট বা প্ল্যান (যেমন: struct), এবং ইনস্ট্যান্টিয়েশন হলো সেই প্ল্যান অনুযায়ী একটি বাস্তব অবজেক্ট তৈরি করা।
- উদাহরণস্বরূপ, যদি আমরা একটি struct ডিক্লেয়ার করি যা "ব্যক্তি" (Person) প্রতিনিধিত্ব করে, তাহলে একটি বাস্তব ব্যক্তির ডেটা ধারণ করার জন্য যে ভেরিয়েবলটি তৈরি করা হয়, সেটি হলো ওই struct-এর একটি ইনস্ট্যান্স , এবং এই প্রক্রিয়াটিকে বলা হয় ইনস্ট্যান্টিয়েশ।

#### উদাহরণ

```go
package main
import "fmt"
// একটি স্ট্রাক্ট ডিক্লেয়ার করা
type Person struct {
   Name string
   Age  int
}
func main() {
   // স্ট্রাক্টের ইনস্ট্যান্টিয়েশন
   p1 := Person{Name: "John", Age: 30}
   p2 := Person{Name: "Alice", Age: 25}
   fmt.Println("Person 1:", p1)
   fmt.Println("Person 2:", p2)
}
Output:
Person 1: {John 30}
Person 2: {Alice 25}
```

```
ব্যাখ্যা:
Person হলো একটি স্ট্রাক্ট (ব্লুপ্রিন্ট)।
p1 এবং p2 হলো Person স্ট্রাক্টের দুটি ইনস্ট্যান্স।
এই ইনস্ট্যান্স তৈরির প্রক্রিয়াকে বলা হয় ইনস্ট্যান্টিয়েশন।
```

---

### ২৪। What is the receiver function?

Go ভাষায় "receiver function" হল একটি মেথড যেটি একটি নির্দিষ্ট টাইপের সাথে যুক্ত থাকে। এই মেথডগুলি একটি স্ট্রাক্ট (struct) বা অন্য কোনো টাইপের উপর অপারেশন সম্পাদন করতে ব্যবহৃত হয়। রিসিভার ফাংশন ডিফাইন করার সময় ফাংশনের নামের আগে একটি রিসিভার প্যারামিটার যোগ করা হয়, যা নির্দেশ করে যে এই মেথডটি কোন টাইপের সাথে যুক্ত।

#### উদাহরণ

```go
// একটি স্ট্রাক্ট ডিফাইন করা
type Rectangle struct {
   width, height float64
}
// একটি রিসিভার ফাংশন ডিফাইন করা
func (r Rectangle) Area() float64 {
   return r.width * r.height
}
func main() {
   // Rectangle টাইপের একটি ইনস্ট্যান্স তৈরি করা
   rect := Rectangle{width: 10, height: 5}
   // রিসিভার ফাংশন কল করা
   fmt.Println("Area of the rectangle:", rect.Area())
}

```

বিঃদ্রঃ এই উদাহরণে, Area ফাংশনটি Rectangle টাইপের একটি রিসিভার ফাংশন। rect.Area() কল করার মাধ্যমে Rectangle টাইপের rect অবজেক্টের উপর এই মেথডটি কাজ করে।

---

### ২৫। Difference between expression and statement

**Expression (এক্সপ্রেশন):**
Expression হল এমন একটি কোড অংশ যা একটি মান (value) তৈরি করে। এটি একটি ভ্যারিয়েবল, কনস্ট্যান্ট, অপারেটর, বা ফাংশন কলের সমন্বয়ে গঠিত হতে পারে। প্রতিটি এক্সপ্রেশন একটি নির্দিষ্ট মানে রূপান্তরিত হয়, যেমন: সংখ্যা, স্ট্রিং, বুলিয়ান ইত্যাদি।

**Statement (স্টেটমেন্ট):**
Statement হল এমন একটি কোড অংশ যা একটি নির্দিষ্ট কাজ (action) সম্পাদন করে। এটি প্রোগ্রামের এক্সিকিউশন ফ্লো নিয়ন্ত্রণ করে বা কোনো কাজ সম্পাদন করে, যেমন: ভ্যারিয়েবল ডিক্লেয়ার করা, লুপ চালানো, শর্ত পরীক্ষা করা ইত্যাদি। স্টেটমেন্ট সাধারণত কোনো মান তৈরি করে না, বরং এটি প্রোগ্রামের আচরণ পরিবর্তন করে।

## পার্থক্য সংক্ষেপে

| **বিষয়**             | **Expression (এক্সপ্রেশন)**       | **Statement (স্টেটমেন্ট)**     |
| -------------------- | --------------------------------- | ------------------------------ |
| **সংজ্ঞা**           | একটি মান তৈরি করে।                | কোনো কাজ সম্পাদন করে।          |
| **উদাহরণ**           | `x + y`, `5 * 3`                  | `x = 10`, `if x > 5`           |
| **প্রোগ্রামের আচরণ** | প্রোগ্রামের আচরণ পরিবর্তন করে না। | প্রোগ্রামের আচরণ পরিবর্তন করে। |

#### উদাহরণ

```go
package main
import "fmt"

func main() {
 // Expression
   result := 10 + 5 // 10 + 5 হল একটি এক্সপ্রেশন, যা 15 মান তৈরি করে।


   // Statement
   if result > 10 { // এটি একটি স্টেটমেন্ট, যা শর্ত পরীক্ষা করে।

 fmt.Println("Result is greater than 10") // এটি একটি স্টেটমেন্ট।
   }
}

```

---

### ২৬। what is pointer? And difference between pass by value vs pass by reference

**Pointer:**
Pointer হলো একটি ভেরিয়েবল যা অন্য একটি ভেরিয়েবলের মেমোরি অ্যাড্রেস স্টোর করে। সহজ কথায়, পয়েন্টার আমাদের বলে দেয় যে, কোনো ডেটা মেমরির কোন স্থানে আছে, এবং আমরা সেই স্থানে গিয়ে ডেটার সাথে কাজ করতে পারি।

#### উদাহরণ

```go
package main
import "fmt"


func main() {
   x := 10
   p := &x // p হলো x এর মেমোরি অ্যাড্রেস


   fmt.Println("x এর মান:", x)       // আউটপুট: 10
   fmt.Println("x এর মেমোরি অ্যাড্রেস:", p) // আউটপুট: x এর মেমোরি অ্যাড্রেস
   fmt.Println("p এর মাধ্যমে x এর মান:", *p) // আউটপুট: 10
}
```

**বিঃদ্রঃ** এখানে p হল পয়েন্টার এবং \*p দিয়ে আমরা x এর মান অ্যাক্সেস করতে পারি।

### ২৭। Difference between pass by value vs pass by reference

**Pass by value:**
যখন আমরা একটি ফাংশনে কোনো আর্গুমেন্ট পাস বাই ভ্যালু হিসেবে পাঠাই, তখন সেই আর্গুমেন্টের একটি কপি তৈরি হয় এবং ফাংশন সেই কপি নিয়ে কাজ করে। ফাংশনের ভিতরে কপির মান পরিবর্তন হলেও মূল ভেরিয়েবলের মান অপরিবর্তিত থাকে।

#### উদাহরণ

```go
package main

import "fmt"

func changeValue(val int) {
   val = 20 // শুধুমাত্র কপি পরিবর্তন করা হচ্ছে
   fmt.Println("ফাংশনের ভিতরে val:", val) // আউটপুট: 20
}

func main() {
   x := 10
   changeValue(x)
   fmt.Println("ফাংশনের বাইরে x:", x) // আউটপুট: 10 (মূল মান অপরিবর্তিত)
}
```

**Pass by Reference:**
পাস বাই রেফারেন্সে আর্গুমেন্টের মেমরি অ্যাড্রেস (পয়েন্টার) ফাংশনে পাঠানো হয়। ফাংশন সেই অ্যাড্রেস ব্যবহার করে মূল ভেরিয়েবলের মান পরিবর্তন করতে পারে।

#### উদাহরণ

```go
package main

import "fmt"

func changeValue(num *int) {
   *num = 20 // পয়েন্টারের মাধ্যমে মূল ভেরিয়েবলের মান পরিবর্তন করা হল
}
func main() {
   x := 10
   fmt.Println("পরিবর্তনের আগে x:", x) // আউটপুট: 10
   changeValue(&x) // x এর মেমরি অ্যাড্রেস পাঠানো হল
   fmt.Println("পরিবর্তনের পরে x:", x)   // আউটপুট: 20 (মূল মান পরিবর্তিত হয়েছে)

```

#### পার্থক্য সংক্ষেপে

| **বিষয়**                | **Pass By Value**                    | **Pass By Reference**                           |
| ----------------------- | ------------------------------------ | ----------------------------------------------- |
| **ডাটা পাঠানো**         | ভেরিয়েবলের মান পাঠানো হয়।          | ভেরিয়েবলের মেমরি অ্যাড্রেস পাঠানো হয়।         |
| **মূল মান পরিবর্তন**    | মূল ভেরিয়েবলের মান পরিবর্তন হয় না। | মূল ভেরিয়েবলের মান পরিবর্তন হয়।               |
| **ফাংশনে ডাটা ব্যবহার** | মূল ভেরিয়েবলের একটি কপি তৈরি হয়।   | কপি তৈরি হয় না, মূল ভেরিয়েবল ব্যবহার করা হয়। |

---

এই ডকুমেন্টের মাধ্যমে আপনি Go প্রোগ্রামিং ভাষার গুরুত্বপূর্ণ প্রশ্নোত্তর সম্পর্কে জানতে পারবেন, যা আপনার ইন্টারভিউ প্রস্তুতিতে সহায়ক হবে।
