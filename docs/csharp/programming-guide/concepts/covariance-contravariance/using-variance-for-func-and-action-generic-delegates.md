---
title: Func および Action 汎用デリゲート (Visual Basic) の変性の使用
description: コードの柔軟性を高めるための、Func および Action 汎用デリゲートの共変性と反変性の使用について説明します。
ms.date: 07/20/2015
ms.assetid: 1826774f-2b7a-470f-b110-17cfdd6abdae
ms.openlocfilehash: 613470d7870aa6a917d19904a92e56f0e61f1ed9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176345"
---
# <a name="using-variance-for-func-and-action-generic-delegates-c"></a><span data-ttu-id="c3890-103">Func および Action 汎用デリゲート (Visual Basic) の変性の使用</span><span class="sxs-lookup"><span data-stu-id="c3890-103">Using Variance for Func and Action Generic Delegates (C#)</span></span>

<span data-ttu-id="c3890-104">以下の例では、`Func` 汎用デリゲートと `Action` 汎用デリゲートの共変性と反変性を使用して、メソッドの再利用を可能にし、コードの柔軟性を高める方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c3890-104">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>  
  
 <span data-ttu-id="c3890-105">共変性と反変性の詳細については、「[デリゲートの変性 (C# )](./variance-in-delegates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3890-105">For more information about covariance and contravariance, see [Variance in Delegates (C#)](./variance-in-delegates.md).</span></span>  
  
## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="c3890-106">デリゲートと共変の型パラメーターの使用</span><span class="sxs-lookup"><span data-stu-id="c3890-106">Using Delegates with Covariant Type Parameters</span></span>  

 <span data-ttu-id="c3890-107">次の例は、`Func` 汎用デリゲートにおける共変性のサポートの利点を示しています。</span><span class="sxs-lookup"><span data-stu-id="c3890-107">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="c3890-108">`FindByTitle` メソッドは、`String` 型のパラメーターを受け取り、`Employee` 型のオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c3890-108">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="c3890-109">ただし、このメソッドは `Func<String, Person>` デリゲートに割り当てることもできます。これは `Employee` が `Person` を継承するためです。</span><span class="sxs-lookup"><span data-stu-id="c3890-109">However, you can assign this method to the `Func<String, Person>` delegate because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static Employee FindByTitle(String title)  
    {  
        // This is a stub for a method that returns  
        // an employee that has the specified title.  
        return new Employee();  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Func<String, Employee> findEmployee = FindByTitle;  
  
        // The delegate expects a method to return Person,  
        // but you can assign it a method that returns Employee.  
        Func<String, Person> findPerson = FindByTitle;  
  
        // You can also assign a delegate
        // that returns a more derived type
        // to a delegate that returns a less derived type.  
        findPerson = findEmployee;  
  
    }  
}  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="c3890-110">デリゲートと反変の型パラメーターの使用</span><span class="sxs-lookup"><span data-stu-id="c3890-110">Using Delegates with Contravariant Type Parameters</span></span>  

 <span data-ttu-id="c3890-111">次の例は、`Action` 汎用デリゲートにおける反変性のサポートの利点を示しています。</span><span class="sxs-lookup"><span data-stu-id="c3890-111">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="c3890-112">`AddToContacts` メソッドは、`Person` 型のパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c3890-112">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="c3890-113">ただし、このメソッドは `Action<Employee>` デリゲートに割り当てることもできます。これは `Employee` が `Person` を継承するためです。</span><span class="sxs-lookup"><span data-stu-id="c3890-113">However, you can assign this method to the `Action<Employee>` delegate because `Employee` inherits `Person`.</span></span>  
  
```csharp  
public class Person { }  
public class Employee : Person { }  
class Program  
{  
    static void AddToContacts(Person person)  
    {  
        // This method adds a Person object  
        // to a contact list.  
    }  
  
    static void Test()  
    {  
        // Create an instance of the delegate without using variance.  
        Action<Person> addPersonToContacts = AddToContacts;  
  
        // The Action delegate expects
        // a method that has an Employee parameter,  
        // but you can assign it a method that has a Person parameter  
        // because Employee derives from Person.  
        Action<Employee> addEmployeeToContacts = AddToContacts;  
  
        // You can also assign a delegate
        // that accepts a less derived parameter to a delegate
        // that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3890-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3890-114">See also</span></span>

- [<span data-ttu-id="c3890-115">共変性と反変性 (C#)</span><span class="sxs-lookup"><span data-stu-id="c3890-115">Covariance and Contravariance (C#)</span></span>](./index.md)
- [<span data-ttu-id="c3890-116">ジェネリック</span><span class="sxs-lookup"><span data-stu-id="c3890-116">Generics</span></span>](../../../../standard/generics/index.md)
