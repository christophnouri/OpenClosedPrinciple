# Open/Closed Principle

<!--## 📘 What is OCP? -->

**OCP (Open/Closed Principle)** is the second principle of SOLID.  
It means:
> *Software entities (like classes, modules, functions) should be open for extension, but closed for modification.*

This means we can **add new features or behaviors** to a class **without changing its existing code**.  
This helps keep the code **safe from bugs** and **easy to maintain** when new requirements come.

---

## <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Smileys/Exploding%20Head.webp" alt="Exploding Head" width="35" height="35" /></a> Why is OCP Important?

- Prevents breaking existing code when adding new features
- Makes the system more **flexible**, **scalable**, and **stable**
- Helps developers follow **clean code** and **good architecture**

---

## <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Symbols/Exclamation%20Question%20Mark.webp" alt="Exclamation Question Mark" width="35" height="35" /></a> How This Project Uses OCP

In this example, we want to calculate different discounts for different product types.  
We follow OCP by:

### <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Symbols/Cross%20Mark.webp" alt="Cross Mark" width="35" height="35" /></a> Bad Way (Commented Code):
```csharp
// if (ProductType == 1) return (Price / 100) * 5;
// if (ProductType == 2) return (Price / 100) * 10;
// if (ProductType == 3) return (Price / 100) * 15;
```
In this code, we must modify the method every time we add a new product type.
This violates the Open/Closed Principle.

### <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Symbols/Check%20Box%20With%20Check.webp" alt="Check Box With Check" width="35" height="35" /></a> Good Way (Used in This Project):
```csharp
We use inheritance and method overriding instead:
public class Product
{
    public virtual double GetDiscount() => 0;
}

public class ProductType1 : Product
{
    public override double GetDiscount() => (Price / 100) * 5;
}
```
Now we can add new product types by just creating a new class.
We don’t touch the base Product class anymore!

---

## <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Travel%20and%20Places/Rocket.webp" alt="Rocket" width="35" height="35" /></a> Summary

| Class          | Responsibility                         |
| -------------- | -------------------------------------- |
| `Product`      | Base class with default discount logic |
| `ProductType1` | Overrides discount with 5%             |
| `ProductType2` | Overrides discount with 10%            |
| `ProductType3` | Overrides discount with 15%            |

---

## <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Objects/File%20Folder.webp" alt="File Folder" width="35" height="35" /></a> Project Structure

```text
OpenClosedPrinciple/
│
├── Program.cs         // Entry point
├── Product.cs         // Base product logic
├── ProductType1.cs    // 5% discount
├── ProductType2.cs    // 10% discount
├── ProductType3.cs    // 15% discount
```
---
Thanks for checking out this project!  
If you found it helpful, feel free to <a href="https://www.linkedin.com/in/soheilsadeghii/"><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Telegram-Animated-Emojis/main/Animals%20and%20Nature/Star.webp" alt="Star" width="15" height="15" /></a> the repo or share it with others.  
Contributions, feedback, and suggestions are always welcome!
<br>
<br>
<!-- ![Visitor Badge](https://visitor-badge.laobi.icu/badge?page_id=SoheilSadeghii.OpenClosedPrinciple) -->
