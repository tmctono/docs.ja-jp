---
title: パターン マッチング機能を使用してデータ型を拡張する
description: この高度なチュートリアルでは、パターン マッチング手法を使用して、別々に作成されたデータとアルゴリズムを使用して機能を作成する方法を示します。
ms.date: 03/13/2019
ms.custom: mvc
ms.openlocfilehash: c42a917deee763e7c3e4e24949ec5c896d55016f
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2019
ms.locfileid: "67397835"
---
# <a name="tutorial-using-pattern-matching-features-to-extend-data-types"></a><span data-ttu-id="bc59b-103">チュートリアル: パターン マッチング機能を使用してデータ型を拡張する</span><span class="sxs-lookup"><span data-stu-id="bc59b-103">Tutorial: Using pattern matching features to extend data types</span></span>

<span data-ttu-id="bc59b-104">C# 7 で、基本的なパターン マッチング機能が導入されました。</span><span class="sxs-lookup"><span data-stu-id="bc59b-104">C# 7 introduced basic pattern matching features.</span></span> <span data-ttu-id="bc59b-105">C# 8 では、これらの機能が新しい式とパターンで拡張されています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-105">Those features are extended in C# 8 with new expressions and patterns.</span></span> <span data-ttu-id="bc59b-106">他のライブラリ内に存在する可能性がある型を拡張したかのように動作する機能を記述できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-106">You can write functionality that behaves as though you extended types that may be in other libraries.</span></span> <span data-ttu-id="bc59b-107">パターンの別の用途は、アプリケーションで必要な、拡張される型の基本機能ではない機能を作成することです。</span><span class="sxs-lookup"><span data-stu-id="bc59b-107">Another use for patterns is to create functionality your application requires that isn't a fundamental feature of the type being extended.</span></span>

<span data-ttu-id="bc59b-108">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-108">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="bc59b-109">パターン マッチングを使用する必要がある状況を認識する。</span><span class="sxs-lookup"><span data-stu-id="bc59b-109">Recognize situations where pattern matching should be used.</span></span>
> * <span data-ttu-id="bc59b-110">パターン マッチング式を使用して、型とプロパティの値に基づく動作を実装する。</span><span class="sxs-lookup"><span data-stu-id="bc59b-110">Use pattern matching expressions to implement behavior based on types and property values.</span></span>
> * <span data-ttu-id="bc59b-111">パターン マッチングと他の手法を組み合わせて、完全なアルゴリズムを作成する。</span><span class="sxs-lookup"><span data-stu-id="bc59b-111">Combine pattern matching with other techniques to create complete algorithms.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bc59b-112">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bc59b-112">Prerequisites</span></span>

<span data-ttu-id="bc59b-113">お使いのコンピューターを、.NET Core が実行されるように設定する必要があります。C# 8.0 プレビュー コンパイラも実行されるようにします。</span><span class="sxs-lookup"><span data-stu-id="bc59b-113">You'll need to set up your machine to run .NET Core, including the C# 8.0 preview compiler.</span></span> <span data-ttu-id="bc59b-114">C# 8 プレビュー コンパイラは、最新の [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) または最新の [.NET Core 3.0 プレビュー](https://dotnet.microsoft.com/download/dotnet-core/3.0)で使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-114">The C# 8 preview compiler is available with the latest [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), or the latest [.NET Core 3.0 preview](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="bc59b-115">このチュートリアルでは、.NET と、C# と Visual Studio または .NET Core CLI のいずれかに精通していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-115">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="scenarios-for-pattern-matching"></a><span data-ttu-id="bc59b-116">パターン マッチングのシナリオ</span><span class="sxs-lookup"><span data-stu-id="bc59b-116">Scenarios for pattern matching</span></span>

<span data-ttu-id="bc59b-117">多くの場合、最新の開発には、1 つのまとまりのあるアプリケーションの中で、複数のソースから受信するデータを統合し、それらのデータに基づいて情報と分析情報を提示することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-117">Modern development often includes integrating data from multiple sources and presenting information and insights from that data in a single cohesive application.</span></span> <span data-ttu-id="bc59b-118">開発者やチームは、受信データを表す型のすべてをコントロールしたり、アクセスしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bc59b-118">You and your team won't have control or access for all the types that represent the incoming data.</span></span>

<span data-ttu-id="bc59b-119">従来のオブジェクト指向設計では、複数のデータ ソースから受信する各データ型を表す型をアプリケーション内で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc59b-119">The classic object-oriented design would call for creating types in your application that represent each data type from those multiple data sources.</span></span> <span data-ttu-id="bc59b-120">その後、アプリケーションで、それらの新しい型を操作し、継承階層を構築し、仮想メソッドを作成し、抽象化を実装します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-120">Then, your application would work with those new types, build inheritance hierarchies, create virtual methods, and implement abstractions.</span></span> <span data-ttu-id="bc59b-121">これらの手法は有効であり、ときには最善のツールです。</span><span class="sxs-lookup"><span data-stu-id="bc59b-121">Those techniques work, and sometimes they are the best tools.</span></span> <span data-ttu-id="bc59b-122">少ないコードを記述できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bc59b-122">Other times you can write less code.</span></span> <span data-ttu-id="bc59b-123">データと、そのデータを操作する操作を分離する手法を使用して、もっと読みやすいコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-123">You can write more clear code using techniques that separate the data from the operations that manipulate that data.</span></span>

<span data-ttu-id="bc59b-124">このチュートリアルでは、1 つのシナリオでさまざまな外部ソースから受信データを受け取るアプリケーションを作成して探索します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-124">In this tutorial, you'll create and explore an application that takes incoming data from several external sources for a single scenario.</span></span> <span data-ttu-id="bc59b-125">**パターン マッチング**を使用して、元のシステムには含まれていない効率的な方法で、データを使用して処理するしくみを見ていきます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-125">You'll see how **pattern matching** provides an efficient way to consume and process that data in ways that weren't part of the original system.</span></span>

<span data-ttu-id="bc59b-126">通行料金とピーク時間帯料金を使用して交通量を管理する大都市圏について検討します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-126">Consider a major metropolitan area that is using tolls and peak time pricing to manage traffic.</span></span> <span data-ttu-id="bc59b-127">車種に基づいて通行料金を計算するアプリケーションを記述します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-127">You write an application that calculates tolls for a vehicle based on its type.</span></span> <span data-ttu-id="bc59b-128">機能強化として、車両の乗員数に基づく料金を組み込みます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-128">Later enhancements incorporate pricing based on the number of occupants in the vehicle.</span></span> <span data-ttu-id="bc59b-129">さらなる機能強化として、時間帯と曜日に基づく料金を追加します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-129">Further enhancements add pricing based on the time and the day of the week.</span></span>

<span data-ttu-id="bc59b-130">この簡単な説明から、このシステムをモデル化するオブジェクト階層をすぐに思い描くことができます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-130">From that brief description, you may have quickly sketched out an object hierarchy to model this system.</span></span> <span data-ttu-id="bc59b-131">ただし、データは、他の車両登録管理システムなどの複数のソースから送信されます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-131">However, your data is coming from multiple sources like other vehicle registration management systems.</span></span> <span data-ttu-id="bc59b-132">これらのシステムでは異なるクラスを使用してデータがモデル化されているため、使用できる単一のオブジェクト モデルはありません。</span><span class="sxs-lookup"><span data-stu-id="bc59b-132">These systems provide different classes to model that data and you don't have a single object model you can use.</span></span> <span data-ttu-id="bc59b-133">このチュートリアルでは、次のコードに示すように、簡略化されたクラスを使用して外部システムからの車両データをモデル化します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-133">In this tutorial, you'll use these simplified classes to model for the vehicle data from these external systems, as shown in the following code:</span></span>

[!code-csharp[ExternalSystems](~/samples/csharp/tutorials/patterns/start/toll-calculator/ExternalSystems.cs)]

<span data-ttu-id="bc59b-134">GitHub の [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) リポジトリから、スタート コードをダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-134">You can download the starter code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) GitHub repository.</span></span> <span data-ttu-id="bc59b-135">さまざまなシステムからの車両クラスがあり、異なる名前空間に存在していることがわかります。</span><span class="sxs-lookup"><span data-stu-id="bc59b-135">You can see that the vehicle classes are from different systems, and are in different namespaces.</span></span> <span data-ttu-id="bc59b-136">`System.Object` を除いて、利用できる共通基底クラスはありません。</span><span class="sxs-lookup"><span data-stu-id="bc59b-136">No common base class, other than `System.Object` can be leveraged.</span></span>

## <a name="pattern-matching-designs"></a><span data-ttu-id="bc59b-137">パターン マッチング設計</span><span class="sxs-lookup"><span data-stu-id="bc59b-137">Pattern matching designs</span></span>

<span data-ttu-id="bc59b-138">このチュートリアルで使用するシナリオでは、パターン マッチングを使用して解決するのに適した種類の問題に焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-138">The scenario used in this tutorial highlights the kinds of problems that pattern matching is well-suited to solve:</span></span>

- <span data-ttu-id="bc59b-139">操作する必要があるオブジェクトは、目標と一致するオブジェクト階層内にはありません。</span><span class="sxs-lookup"><span data-stu-id="bc59b-139">The objects you need to work with aren't in an object hierarchy that matches your goals.</span></span> <span data-ttu-id="bc59b-140">別個のシステムの一部であるクラスを操作する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bc59b-140">You may be working with classes that are part of unrelated systems.</span></span>
- <span data-ttu-id="bc59b-141">追加する機能は、これらのクラスのコア抽象化の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="bc59b-141">The functionality you're adding isn't part of the core abstraction for these classes.</span></span> <span data-ttu-id="bc59b-142">車両が支払う通行料金は、車両の種類によって "*変化*" しますが、通行料金は車両の中心的な関数ではありません。</span><span class="sxs-lookup"><span data-stu-id="bc59b-142">The toll paid by a vehicle *changes* for different types of vehicles, but the toll isn't a core function of the vehicle.</span></span>

<span data-ttu-id="bc59b-143">データの "*形状*" とデータに対する "*操作*" が一緒に記述されていない場合は、C# のパターン マッチング機能によって、作業が容易になります。</span><span class="sxs-lookup"><span data-stu-id="bc59b-143">When the *shape* of the data and the *operations* on that data are not described together, the pattern matching features in C# make it easier to work with.</span></span>

## <a name="implement-the-basic-toll-calculations"></a><span data-ttu-id="bc59b-144">基本的な通行料金計算を実装する</span><span class="sxs-lookup"><span data-stu-id="bc59b-144">Implement the basic toll calculations</span></span>

<span data-ttu-id="bc59b-145">最も基本的な通行料金計算は、車種にのみ依存します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-145">The most basic toll calculation relies only on the vehicle type:</span></span>

- <span data-ttu-id="bc59b-146">`Car` は $2.00。</span><span class="sxs-lookup"><span data-stu-id="bc59b-146">A `Car` is $2.00.</span></span>
- <span data-ttu-id="bc59b-147">`Taxi` は $3.50。</span><span class="sxs-lookup"><span data-stu-id="bc59b-147">A `Taxi` is $3.50.</span></span>
- <span data-ttu-id="bc59b-148">`Bus` は $5.00。</span><span class="sxs-lookup"><span data-stu-id="bc59b-148">A `Bus` is $5.00.</span></span>
- <span data-ttu-id="bc59b-149">`DeliveryTruck` は $10.00。</span><span class="sxs-lookup"><span data-stu-id="bc59b-149">A `DeliveryTruck` is $10.00</span></span>

<span data-ttu-id="bc59b-150">新しい `TollCalculator` クラスを作成し、車種に対するパターン マッチングを実装して、通行料金の金額を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-150">Create a new `TollCalculator` class, and implement pattern matching on the vehicle type to get the toll amount.</span></span> <span data-ttu-id="bc59b-151">`TollCalculator` の最初の実装を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-151">The following code shows the initial implementation of the `TollCalculator`.</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    public class TollCalculator
    {
        public decimal CalculateToll(object vehicle) =>
            vehicle switch
        {
            Car c           => 2.00m,
            Taxi t          => 3.50m,
            Bus b           => 5.00m,
            DeliveryTruck t => 10.00m,
            { }             => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
            null            => throw new ArgumentNullException(nameof(vehicle))
        };
    }
}
```

<span data-ttu-id="bc59b-152">上記のコードでは、**型パターン**をテストする **switch 式** ([`switch`](../language-reference/keywords/switch.md) ステートメントとは異なります) が使用されています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-152">The preceding code uses a **switch expression** (not the same as a [`switch`](../language-reference/keywords/switch.md) statement) that tests the **type pattern**.</span></span> <span data-ttu-id="bc59b-153">上記のコードでは、**switch 式**は変数 `vehicle` で始まり、`switch` キーワードが続きます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-153">A **switch expression** begins with the variable, `vehicle` in the preceding code, followed by the `switch` keyword.</span></span> <span data-ttu-id="bc59b-154">次に、すべての **switch アーム**が中かっこ内に指定されます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-154">Next comes all the **switch arms** inside curly braces.</span></span> <span data-ttu-id="bc59b-155">`switch` 式は、`switch` ステートメントを囲む構文に対して、その他の絞り込みを行います。</span><span class="sxs-lookup"><span data-stu-id="bc59b-155">The `switch` expression makes other refinements to the syntax that surrounds the `switch` statement.</span></span> <span data-ttu-id="bc59b-156">`case` キーワードは省略され、各アームの結果が式になります。</span><span class="sxs-lookup"><span data-stu-id="bc59b-156">The `case` keyword is omitted, and the result of each arm is an expression.</span></span> <span data-ttu-id="bc59b-157">最後の 2 つのアームは、新しい言語機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-157">The last two arms show a new language feature.</span></span> <span data-ttu-id="bc59b-158">`{ }` case は、前のアームと一致しなかった null 以外のオブジェクトと一致します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-158">The `{ }` case matches any non-null object that didn't match an earlier arm.</span></span> <span data-ttu-id="bc59b-159">このアームは、このメソッドに渡された正しくない型をキャッチします。</span><span class="sxs-lookup"><span data-stu-id="bc59b-159">This arm catches any incorrect types passed to this method.</span></span>  <span data-ttu-id="bc59b-160">`{ }` case は、車種ごとの case に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc59b-160">The `{ }` case must follow the cases for each vehicle type.</span></span> <span data-ttu-id="bc59b-161">順序が逆になった場合は、`{ }` case が優先されます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-161">If the order were reversed, the `{ }` case would take precedence.</span></span> <span data-ttu-id="bc59b-162">最後に、`null` パターンで、このメソッドに `null` が渡されたときを検出します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-162">Finally, the `null` pattern detects when a `null` is passed to this method.</span></span> <span data-ttu-id="bc59b-163">他の型パターンが null 以外の正しい車種のオブジェクトのみと一致するため、`null` パターンを最後にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-163">The `null` pattern can be last because the other type patterns match only a non-null object of the correct type.</span></span>

<span data-ttu-id="bc59b-164">このコードを `Program.cs` の次のコードを使用してテストできます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-164">You can test this code using the following code in `Program.cs`:</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    class Program
    {
        static void Main(string[] args)
        {
            var tollCalc = new TollCalculator();

            var car = new Car();
            var taxi = new Taxi();
            var bus = new Bus();
            var truck = new DeliveryTruck();

            Console.WriteLine($"The toll for a car is {tollCalc.CalculateToll(car)}");
            Console.WriteLine($"The toll for a taxi is {tollCalc.CalculateToll(taxi)}");
            Console.WriteLine($"The toll for a bus is {tollCalc.CalculateToll(bus)}");
            Console.WriteLine($"The toll for a truck is {tollCalc.CalculateToll(truck)}");

            try
            {
                tollCalc.CalculateToll("this will fail");
            }
            catch (ArgumentException e)
            {
                Console.WriteLine("Caught an argument exception when using the wrong type");
            }
            try
            {
                tollCalc.CalculateToll(null);
            }
            catch (ArgumentNullException e)
            {
                Console.WriteLine("Caught an argument exception when using null");
            }
        }
    }
}
```

<span data-ttu-id="bc59b-165">このコードはスタート プロジェクトに含まれていますが、コメント アウトされています。コメントを削除することで、自分で記述したコードをテストできます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-165">That code is included in the starter project, but is commented out. Remove the comments, and you can test what you've written.</span></span>

<span data-ttu-id="bc59b-166">コードとデータが分離されるアルゴリズムの作成にパターンがどのように役立つかを示す最初の例を見てきました。</span><span class="sxs-lookup"><span data-stu-id="bc59b-166">You're starting to see how patterns can help you create algorithms where the code and the data are separate.</span></span> <span data-ttu-id="bc59b-167">`switch` 式によって型がテストされ、結果に基づいて別の値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-167">The `switch` expression tests the type and produces different values based on the results.</span></span> <span data-ttu-id="bc59b-168">これはほんの序の口に過ぎません。</span><span class="sxs-lookup"><span data-stu-id="bc59b-168">That's only the beginning.</span></span>

## <a name="add-occupancy-pricing"></a><span data-ttu-id="bc59b-169">乗員料金を追加する</span><span class="sxs-lookup"><span data-stu-id="bc59b-169">Add occupancy pricing</span></span>

<span data-ttu-id="bc59b-170">料金徴収機関は、車両が乗車定員を乗せて走行することを推奨したいと思っています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-170">The toll authority wants to encourage vehicles to travel at maximum capacity.</span></span> <span data-ttu-id="bc59b-171">車両の乗員数が少ない場合は多く請求し、乗車定員の場合は料金を下げることによって、定員いっぱいでの走行を推奨することを決定しています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-171">They've decided to charge more when vehicles have fewer passengers, and encourage full vehicles by offering lower pricing:</span></span>

- <span data-ttu-id="bc59b-172">乗客がいない自動車とタクシーは、$0.50 余分に支払う。</span><span class="sxs-lookup"><span data-stu-id="bc59b-172">Cars and taxis with no passengers pay an extra $0.50.</span></span>
- <span data-ttu-id="bc59b-173">2 名の乗客がいる自動車とタクシーは、$0.50 割引される。</span><span class="sxs-lookup"><span data-stu-id="bc59b-173">Cars and taxis with two passengers get a $0.50 discount.</span></span>
- <span data-ttu-id="bc59b-174">3 名以上の乗客がいる自動車とタクシーは、$1.00 割引される。</span><span class="sxs-lookup"><span data-stu-id="bc59b-174">Cars and taxis with three or more passengers get a $1.00 discount.</span></span>
- <span data-ttu-id="bc59b-175">乗車率が 50% 未満のバスは、$2.00 余分に支払う。</span><span class="sxs-lookup"><span data-stu-id="bc59b-175">Buses that are less than 50% full pay an extra $2.00.</span></span>
- <span data-ttu-id="bc59b-176">乗車率が 90% を超えるバスは、$1.00 割引される。</span><span class="sxs-lookup"><span data-stu-id="bc59b-176">Buses that are more than 90% full get a $1.00 discount.</span></span>

<span data-ttu-id="bc59b-177">このルールは、同じ switch 式で**プロパティ パターン**を使用して実装できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-177">These rules can be implemented using the **property pattern** in the same switch expression.</span></span> <span data-ttu-id="bc59b-178">プロパティ パターンでは、型が決定した後、オブジェクトのプロパティが調べられます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-178">The property pattern examines properties of the object once the type has been determined.</span></span> <span data-ttu-id="bc59b-179">`Car` に対する 1 つの case が、4 つの異なる case に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-179">The single case for a `Car` expands to four different cases:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1 }       => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c                       => 2.00m - 1.0m,

    // ...
};
```

<span data-ttu-id="bc59b-180">最初の 3 つの case では、型を `Car` としてテストした後、`Passengers` プロパティの値がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-180">The first three cases test the type as a `Car`, then check the value of the `Passengers` property.</span></span> <span data-ttu-id="bc59b-181">両方が一致した場合は、その式が評価され、結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-181">If both match, that expression is evaluated and returned.</span></span>

<span data-ttu-id="bc59b-182">タクシーに対する case も、同様の方法で拡張します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-182">You would also expand the cases for taxis in a similar manner:</span></span>

```csharp
vehicle switch
{
    // ...

    Taxi { Fares: 0}  => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2}  => 3.50m - 0.50m,
    Taxi t            => 3.50m - 1.00m,

    // ...
};
```

<span data-ttu-id="bc59b-183">上記の例では、最後の case の `when` 句は省略されています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-183">In the preceding example, the `when` clause was omitted on the final case.</span></span>

<span data-ttu-id="bc59b-184">次に、次の例に示すように、バスに対する case を拡張して、乗車率ルールを実装します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-184">Next, implement the occupancy rules by expanding the cases for buses, as shown in the following example:</span></span>

```csharp
vehicle switch
{
    // ...

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    // ...
};
```

<span data-ttu-id="bc59b-185">料金徴収機関は、配送トラックの乗客数には関心がありません。</span><span class="sxs-lookup"><span data-stu-id="bc59b-185">The toll authority isn't concerned with the number of passengers in the delivery trucks.</span></span> <span data-ttu-id="bc59b-186">代わりに、次のようにトラックの重量クラスに基づいて通行料金の金額を調整します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-186">Instead, they adjust the toll amount based on the weight class of the trucks as follows:</span></span>

- <span data-ttu-id="bc59b-187">5,000 lbs を超えるトラックは、$5.00 余分に請求される。</span><span class="sxs-lookup"><span data-stu-id="bc59b-187">Trucks over 5000 lbs are charged an extra $5.00.</span></span>
- <span data-ttu-id="bc59b-188">3,000 lbs を下回る軽トラックは、$2.00 割引される。</span><span class="sxs-lookup"><span data-stu-id="bc59b-188">Light trucks under 3000 lbs are given a $2.00 discount.</span></span>

<span data-ttu-id="bc59b-189">これらのルールは、次のコードで実装されます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-189">That rule is implemented with the following code:</span></span>

```csharp
vehicle switch
{
    // ...

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

<span data-ttu-id="bc59b-190">前のコードは、switch アームの `when` 句を示しています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-190">The preceding code shows the `when` clause of a switch arm.</span></span> <span data-ttu-id="bc59b-191">`when` 句を使用して、プロパティの等価以外の条件をテストできます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-191">You use the `when` clause to test conditions other than equality on a property.</span></span> <span data-ttu-id="bc59b-192">完了すると、以下によく似たメソッドが作成されます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-192">When you've finished, you'll have a method that looks much like the following:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1}        => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c                       => 2.00m - 1.0m,

    Taxi { Fares: 0}  => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2}  => 3.50m - 0.50m,
    Taxi t            => 3.50m - 1.00m,

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

<span data-ttu-id="bc59b-193">これらの switch アームの多くは、**再帰パターン**の例です。</span><span class="sxs-lookup"><span data-stu-id="bc59b-193">Many of these switch arms are examples of **recursive patterns**.</span></span> <span data-ttu-id="bc59b-194">たとえば、`Car { Passengers: 1}` は、プロパティ パターンの内部の定数パターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-194">For example, `Car { Passengers: 1}` shows a constant pattern inside a property pattern.</span></span>

<span data-ttu-id="bc59b-195">switch を入れ子にして使用することで、このコードの反復を少なくすることができます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-195">You can make this code less repetitive by using nested switches.</span></span> <span data-ttu-id="bc59b-196">`Car` と `Taxi` は、どちらにも上記の例で示した 4 つの異なるアームがあります。</span><span class="sxs-lookup"><span data-stu-id="bc59b-196">The `Car` and `Taxi` both have four different arms in the preceding examples.</span></span> <span data-ttu-id="bc59b-197">両方に対して、プロパティ パターンに供給される型パターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-197">In both cases, you can create a type pattern that feeds into a property pattern.</span></span> <span data-ttu-id="bc59b-198">この手法を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-198">This technique is shown in the following code:</span></span>

```csharp
public decimal CalculateToll(object vehicle) =>
    vehicle switch
    {
        Car c => c.Passengers switch
        {
            0 => 2.00m + 0.5m,
            1 => 2.0m,
            2 => 2.0m - 0.5m,
            _ => 2.00m - 1.0m
        },

        Taxi t => t.Fares switch
        {
            0 => 3.50m + 1.00m,
            1 => 3.50m,
            2 => 3.50m - 0.50m,
            _ => 3.50m - 1.00m
        },

        Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
        Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
        Bus b => 5.00m,

        DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
        DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
        DeliveryTruck t => 10.00m,

        { }  => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
        null => throw new ArgumentNullException(nameof(vehicle))
    };
```

<span data-ttu-id="bc59b-199">上記の例では、再帰式の使用は、プロパティの値をテストする子アームを含む `Car` と `Taxi` のアームを繰り返さないことを意味しています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-199">In the preceding sample, using a recursive expression means you don't repeat the `Car` and `Taxi` arms containing child arms that test the property value.</span></span> <span data-ttu-id="bc59b-200">この手法は、プロパティの個別の値ではなくその範囲をテストする `Bus` と `DeliveryTruck` のアームでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="bc59b-200">This technique isn't used for the `Bus` and `DeliveryTruck` arms because those arms are testing ranges for the property, not discrete values.</span></span>

## <a name="add-peak-pricing"></a><span data-ttu-id="bc59b-201">ピーク料金を追加する</span><span class="sxs-lookup"><span data-stu-id="bc59b-201">Add peak pricing</span></span>

<span data-ttu-id="bc59b-202">最後の機能として、料金徴収機関は、時間に依存するピーク料金を追加することを望んでいます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-202">For the final feature, the toll authority wants to add time sensitive peak pricing.</span></span> <span data-ttu-id="bc59b-203">朝と夕方のラッシュ アワーの間は、通行料金を倍にします。</span><span class="sxs-lookup"><span data-stu-id="bc59b-203">During the morning and evening rush hours, the tolls are doubled.</span></span> <span data-ttu-id="bc59b-204">このルールは、片方向の通行のみに影響し、朝のラッシュ時は市内に入る (インバウンド) 通行が、夕方のラッシュ時は市外に出てゆく (アウトバウンド) 通行が対象になります。</span><span class="sxs-lookup"><span data-stu-id="bc59b-204">That rule only affects traffic in one direction: inbound to the city in the morning, and outbound in the evening rush hour.</span></span> <span data-ttu-id="bc59b-205">平日のその他の時間帯では、通行料金は 50% 増額される。</span><span class="sxs-lookup"><span data-stu-id="bc59b-205">During other times during the workday, tolls increase by 50%.</span></span> <span data-ttu-id="bc59b-206">深夜と早朝の通行料金は、25% 減額される。</span><span class="sxs-lookup"><span data-stu-id="bc59b-206">Late night and early morning, tolls are reduced by 25%.</span></span> <span data-ttu-id="bc59b-207">週末は、時間に関係なく、通常料金になる。</span><span class="sxs-lookup"><span data-stu-id="bc59b-207">During the weekend, it's the normal rate, regardless of the time.</span></span>

<span data-ttu-id="bc59b-208">この機能のためにパターン マッチングを使用しますが、それは他の手法と統合します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-208">You'll use pattern matching for this feature, but you'll integrate it with other techniques.</span></span> <span data-ttu-id="bc59b-209">方向、曜日、および時間帯のすべてを組み合わせた単一のパターン マッチ式を作成できますが、</span><span class="sxs-lookup"><span data-stu-id="bc59b-209">You could build a single pattern match expression that would account for all the combinations of direction, day of the week, and time.</span></span> <span data-ttu-id="bc59b-210">結果は、複雑な式になるでしょう。</span><span class="sxs-lookup"><span data-stu-id="bc59b-210">The result would be a complicated expression.</span></span> <span data-ttu-id="bc59b-211">読みにくく、理解しにくくなるでしょう。</span><span class="sxs-lookup"><span data-stu-id="bc59b-211">It would be hard to read and difficult to understand.</span></span> <span data-ttu-id="bc59b-212">それは、正確さを保証することを難しくします。</span><span class="sxs-lookup"><span data-stu-id="bc59b-212">That makes it hard to ensure correctness.</span></span> <span data-ttu-id="bc59b-213">代わりに、メソッドを組み合わせて、すべての状態を簡潔に記述する値のタプルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-213">Instead, combine those methods to build a tuple of values that concisely describes all those states.</span></span> <span data-ttu-id="bc59b-214">その後、パターン マッチングを使用して、通行料金の乗数を計算できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-214">Then use pattern matching to calculate a multiplier for the toll.</span></span> <span data-ttu-id="bc59b-215">タプルには、3 つの個別の条件が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-215">The tuple contains three discrete conditions:</span></span>

- <span data-ttu-id="bc59b-216">その日が平日または週末のどちらであるか。</span><span class="sxs-lookup"><span data-stu-id="bc59b-216">The day is either a weekday or a weekend.</span></span>
- <span data-ttu-id="bc59b-217">通行料金が収集される時間帯。</span><span class="sxs-lookup"><span data-stu-id="bc59b-217">The band of time when the toll is collected.</span></span>
- <span data-ttu-id="bc59b-218">方向が市内に入るほうか市外に出るほうか。</span><span class="sxs-lookup"><span data-stu-id="bc59b-218">The direction is into the city or out of the city</span></span>

<span data-ttu-id="bc59b-219">次の表に、入力値の組み合わせとピーク時の乗数を示します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-219">The following table shows the combinations of input values and the peak pricing multiplier:</span></span>

| <span data-ttu-id="bc59b-220">Day</span><span class="sxs-lookup"><span data-stu-id="bc59b-220">Day</span></span>        | <span data-ttu-id="bc59b-221">時刻</span><span class="sxs-lookup"><span data-stu-id="bc59b-221">Time</span></span>         | <span data-ttu-id="bc59b-222">方向</span><span class="sxs-lookup"><span data-stu-id="bc59b-222">Direction</span></span> | <span data-ttu-id="bc59b-223">割り増し</span><span class="sxs-lookup"><span data-stu-id="bc59b-223">Premium</span></span> |
| ---------- | ------------ | --------- |--------:|
| <span data-ttu-id="bc59b-224">平日</span><span class="sxs-lookup"><span data-stu-id="bc59b-224">Weekday</span></span>    | <span data-ttu-id="bc59b-225">朝のラッシュ時</span><span class="sxs-lookup"><span data-stu-id="bc59b-225">morning rush</span></span> | <span data-ttu-id="bc59b-226">インバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-226">inbound</span></span>   | <span data-ttu-id="bc59b-227">x 2.00</span><span class="sxs-lookup"><span data-stu-id="bc59b-227">x 2.00</span></span>  |
| <span data-ttu-id="bc59b-228">平日</span><span class="sxs-lookup"><span data-stu-id="bc59b-228">Weekday</span></span>    | <span data-ttu-id="bc59b-229">朝のラッシュ時</span><span class="sxs-lookup"><span data-stu-id="bc59b-229">morning rush</span></span> | <span data-ttu-id="bc59b-230">アウトバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-230">outbound</span></span>  | <span data-ttu-id="bc59b-231">x 1.00</span><span class="sxs-lookup"><span data-stu-id="bc59b-231">x 1.00</span></span>  |
| <span data-ttu-id="bc59b-232">平日</span><span class="sxs-lookup"><span data-stu-id="bc59b-232">Weekday</span></span>    | <span data-ttu-id="bc59b-233">日中</span><span class="sxs-lookup"><span data-stu-id="bc59b-233">daytime</span></span>      | <span data-ttu-id="bc59b-234">インバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-234">inbound</span></span>   | <span data-ttu-id="bc59b-235">x 1.50</span><span class="sxs-lookup"><span data-stu-id="bc59b-235">x 1.50</span></span>  |
| <span data-ttu-id="bc59b-236">平日</span><span class="sxs-lookup"><span data-stu-id="bc59b-236">Weekday</span></span>    | <span data-ttu-id="bc59b-237">日中</span><span class="sxs-lookup"><span data-stu-id="bc59b-237">daytime</span></span>      | <span data-ttu-id="bc59b-238">アウトバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-238">outbound</span></span>  | <span data-ttu-id="bc59b-239">x 1.50</span><span class="sxs-lookup"><span data-stu-id="bc59b-239">x 1.50</span></span>  |
| <span data-ttu-id="bc59b-240">平日</span><span class="sxs-lookup"><span data-stu-id="bc59b-240">Weekday</span></span>    | <span data-ttu-id="bc59b-241">夕方のラッシュ時</span><span class="sxs-lookup"><span data-stu-id="bc59b-241">evening rush</span></span> | <span data-ttu-id="bc59b-242">インバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-242">inbound</span></span>   | <span data-ttu-id="bc59b-243">x 1.00</span><span class="sxs-lookup"><span data-stu-id="bc59b-243">x 1.00</span></span>  |
| <span data-ttu-id="bc59b-244">平日</span><span class="sxs-lookup"><span data-stu-id="bc59b-244">Weekday</span></span>    | <span data-ttu-id="bc59b-245">夕方のラッシュ時</span><span class="sxs-lookup"><span data-stu-id="bc59b-245">evening rush</span></span> | <span data-ttu-id="bc59b-246">アウトバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-246">outbound</span></span>  | <span data-ttu-id="bc59b-247">x 2.00</span><span class="sxs-lookup"><span data-stu-id="bc59b-247">x 2.00</span></span>  |
| <span data-ttu-id="bc59b-248">平日</span><span class="sxs-lookup"><span data-stu-id="bc59b-248">Weekday</span></span>    | <span data-ttu-id="bc59b-249">夜間</span><span class="sxs-lookup"><span data-stu-id="bc59b-249">overnight</span></span>    | <span data-ttu-id="bc59b-250">インバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-250">inbound</span></span>   | <span data-ttu-id="bc59b-251">x 0.75</span><span class="sxs-lookup"><span data-stu-id="bc59b-251">x 0.75</span></span>  |
| <span data-ttu-id="bc59b-252">平日</span><span class="sxs-lookup"><span data-stu-id="bc59b-252">Weekday</span></span>    | <span data-ttu-id="bc59b-253">夜間</span><span class="sxs-lookup"><span data-stu-id="bc59b-253">overnight</span></span>    | <span data-ttu-id="bc59b-254">アウトバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-254">outbound</span></span>  | <span data-ttu-id="bc59b-255">x 0.75</span><span class="sxs-lookup"><span data-stu-id="bc59b-255">x 0.75</span></span>  |
| <span data-ttu-id="bc59b-256">週末</span><span class="sxs-lookup"><span data-stu-id="bc59b-256">Weekend</span></span>    | <span data-ttu-id="bc59b-257">朝のラッシュ時</span><span class="sxs-lookup"><span data-stu-id="bc59b-257">morning rush</span></span> | <span data-ttu-id="bc59b-258">インバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-258">inbound</span></span>   | <span data-ttu-id="bc59b-259">x 1.00</span><span class="sxs-lookup"><span data-stu-id="bc59b-259">x 1.00</span></span>  |
| <span data-ttu-id="bc59b-260">週末</span><span class="sxs-lookup"><span data-stu-id="bc59b-260">Weekend</span></span>    | <span data-ttu-id="bc59b-261">朝のラッシュ時</span><span class="sxs-lookup"><span data-stu-id="bc59b-261">morning rush</span></span> | <span data-ttu-id="bc59b-262">アウトバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-262">outbound</span></span>  | <span data-ttu-id="bc59b-263">x 1.00</span><span class="sxs-lookup"><span data-stu-id="bc59b-263">x 1.00</span></span>  |
| <span data-ttu-id="bc59b-264">週末</span><span class="sxs-lookup"><span data-stu-id="bc59b-264">Weekend</span></span>    | <span data-ttu-id="bc59b-265">日中</span><span class="sxs-lookup"><span data-stu-id="bc59b-265">daytime</span></span>      | <span data-ttu-id="bc59b-266">インバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-266">inbound</span></span>   | <span data-ttu-id="bc59b-267">x 1.00</span><span class="sxs-lookup"><span data-stu-id="bc59b-267">x 1.00</span></span>  |
| <span data-ttu-id="bc59b-268">週末</span><span class="sxs-lookup"><span data-stu-id="bc59b-268">Weekend</span></span>    | <span data-ttu-id="bc59b-269">日中</span><span class="sxs-lookup"><span data-stu-id="bc59b-269">daytime</span></span>      | <span data-ttu-id="bc59b-270">アウトバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-270">outbound</span></span>  | <span data-ttu-id="bc59b-271">x 1.00</span><span class="sxs-lookup"><span data-stu-id="bc59b-271">x 1.00</span></span>  |
| <span data-ttu-id="bc59b-272">週末</span><span class="sxs-lookup"><span data-stu-id="bc59b-272">Weekend</span></span>    | <span data-ttu-id="bc59b-273">夕方のラッシュ時</span><span class="sxs-lookup"><span data-stu-id="bc59b-273">evening rush</span></span> | <span data-ttu-id="bc59b-274">インバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-274">inbound</span></span>   | <span data-ttu-id="bc59b-275">x 1.00</span><span class="sxs-lookup"><span data-stu-id="bc59b-275">x 1.00</span></span>  |
| <span data-ttu-id="bc59b-276">週末</span><span class="sxs-lookup"><span data-stu-id="bc59b-276">Weekend</span></span>    | <span data-ttu-id="bc59b-277">夕方のラッシュ時</span><span class="sxs-lookup"><span data-stu-id="bc59b-277">evening rush</span></span> | <span data-ttu-id="bc59b-278">アウトバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-278">outbound</span></span>  | <span data-ttu-id="bc59b-279">x 1.00</span><span class="sxs-lookup"><span data-stu-id="bc59b-279">x 1.00</span></span>  |
| <span data-ttu-id="bc59b-280">週末</span><span class="sxs-lookup"><span data-stu-id="bc59b-280">Weekend</span></span>    | <span data-ttu-id="bc59b-281">夜間</span><span class="sxs-lookup"><span data-stu-id="bc59b-281">overnight</span></span>    | <span data-ttu-id="bc59b-282">インバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-282">inbound</span></span>   | <span data-ttu-id="bc59b-283">x 1.00</span><span class="sxs-lookup"><span data-stu-id="bc59b-283">x 1.00</span></span>  |
| <span data-ttu-id="bc59b-284">週末</span><span class="sxs-lookup"><span data-stu-id="bc59b-284">Weekend</span></span>    | <span data-ttu-id="bc59b-285">夜間</span><span class="sxs-lookup"><span data-stu-id="bc59b-285">overnight</span></span>    | <span data-ttu-id="bc59b-286">アウトバウンド</span><span class="sxs-lookup"><span data-stu-id="bc59b-286">outbound</span></span>  | <span data-ttu-id="bc59b-287">x 1.00</span><span class="sxs-lookup"><span data-stu-id="bc59b-287">x 1.00</span></span>  |

<span data-ttu-id="bc59b-288">3 つの変数の 16 組の異なる組み合わせがあります。</span><span class="sxs-lookup"><span data-stu-id="bc59b-288">There are 16 different combinations of the three variables.</span></span> <span data-ttu-id="bc59b-289">いくつかの条件を組み合わせることで、最終的な switch 式を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-289">By combining some of the conditions, you'll simplify the final switch expression.</span></span>

<span data-ttu-id="bc59b-290">通行料金を収集するシステムでは、通行料金が徴収される時刻に対して <xref:System.DateTime> 構造体を使用しています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-290">The system that collects the tolls uses a <xref:System.DateTime> structure for the time when the toll was collected.</span></span> <span data-ttu-id="bc59b-291">上記の表から、変数を作成するメンバー メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-291">Build member methods that create the variables from the preceding table.</span></span> <span data-ttu-id="bc59b-292">次の関数では、パターン マッチングの switch 式を使用して、<xref:System.DateTime> が週末または平日のどちらを表しているかを示しています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-292">The following function uses a pattern matching switch expression to express whether a <xref:System.DateTime> represents a weekend or a weekday:</span></span>

```csharp
private static bool IsWeekDay(DateTime timeOfToll) =>
    timeOfToll.DayOfWeek switch
    {
        DayOfWeek.Monday    => true,
        DayOfWeek.Tuesday   => true,
        DayOfWeek.Wednesday => true,
        DayOfWeek.Thursday  => true,
        DayOfWeek.Friday    => true,
        DayOfWeek.Saturday  => false,
        DayOfWeek.Sunday    => false
    };
```

<span data-ttu-id="bc59b-293">このメソッドは機能しますが、繰り返しが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-293">That method works, but it's repetitious.</span></span> <span data-ttu-id="bc59b-294">次のコードに示すように簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-294">You can simplify it, as shown in the following code:</span></span>

[!code-csharp[IsWeekDay](~/samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#IsWeekDay)]

<span data-ttu-id="bc59b-295">次に、時間をブロックに分類する同様の関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-295">Next, add a similar function to categorize the time into the blocks:</span></span>

[!code-csharp[GetTimeBand](~/samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#GetTimeBand)]

<span data-ttu-id="bc59b-296">上記のメソッドでは、パターン マッチングは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="bc59b-296">The previous method doesn't use pattern matching.</span></span> <span data-ttu-id="bc59b-297">使い慣れた `if` ステートメントの連鎖を使用するほうがわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="bc59b-297">It's clearer using a familiar cascade of `if` statements.</span></span> <span data-ttu-id="bc59b-298">プライベート `enum` を追加して、時間の各範囲を個別の値に変換します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-298">You do add a private `enum` to convert each range of time to a discrete value.</span></span>

<span data-ttu-id="bc59b-299">これらのメソッドを作成したら、別の `switch` 式と**タプル パターン**を使用して、割増料金を計算できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-299">After you create those methods, you can use another `switch` expression with the **tuple pattern** to calculate the pricing premium.</span></span> <span data-ttu-id="bc59b-300">全部で 16 のアームがある `switch` 式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-300">You could build a `switch` expression with all 16 arms:</span></span>

[!code-csharp[FullTuplePattern](~/samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#TuplePatternOne)]

<span data-ttu-id="bc59b-301">上記のコードは機能しますが、簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-301">The above code works, but it can be simplified.</span></span> <span data-ttu-id="bc59b-302">週末の 8 つの組み合わせは、同じ通行料金になります。</span><span class="sxs-lookup"><span data-stu-id="bc59b-302">All eight combinations for the weekend have the same toll.</span></span> <span data-ttu-id="bc59b-303">8 つのすべてを、次の行に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-303">You can replace all eight with the following line:</span></span>

```csharp
(false, _, _) => 1.0m,
```

<span data-ttu-id="bc59b-304">平日の日中と夜間のインバウンドとアウトバウンドの通行では、同じ乗数が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-304">Both inbound and outbound traffic have the same multiplier during the weekday daytime and overnight hours.</span></span> <span data-ttu-id="bc59b-305">これら 4 つの switch アームは、次の 2 行に置換できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-305">Those four switch arms can be replaced with the following two lines:</span></span>

```csharp
(true, TimeBand.Overnight, _) => 0.75m,
(true, TimeBand.Daytime, _)   => 1.5m,
```

<span data-ttu-id="bc59b-306">これら 2 つの変更を行った後のコードは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bc59b-306">The code should look like the following code after those two changes:</span></span>

```csharp
public decimal PeakTimePremium(DateTime timeOfToll, bool inbound) =>
    (IsWeekDay(timeOfToll), GetTimeBand(timeOfToll), inbound) switch
    {
        (true, TimeBand.MorningRush, true)  => 2.00m,
        (true, TimeBand.MorningRush, false) => 1.00m,
        (true, TimeBand.Daytime,     _)     => 1.50m,
        (true, TimeBand.EveningRush, true)  => 1.00m,
        (true, TimeBand.EveningRush, false) => 2.00m,
        (true, TimeBand.Overnight,   _)     => 0.75m,
        (false, _,                   _)     => 1.00m,
    };
```

<span data-ttu-id="bc59b-307">最後に、通常料金を支払う 2 つのラッシュの時間帯は削除できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-307">Finally, you can remove the two rush hour times that pay the regular price.</span></span> <span data-ttu-id="bc59b-308">これらのアームを削除した後、最後の switch アーム内の `false` を破棄 (`_`)  に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-308">Once you remove those arms, you can replace the `false` with a discard (`_`) in the final switch arm.</span></span> <span data-ttu-id="bc59b-309">次のメソッドが完成します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-309">You'll have the following finished method:</span></span>

[!code-csharp[SimplifiedTuplePattern](../../../samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#FinalTuplePattern)]

<span data-ttu-id="bc59b-310">この例では、パターン マッチングの利点の 1 つに注目しています。パターンの分岐は、順序正しく評価されます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-310">This example highlights one of the advantages of pattern matching: the pattern branches are evaluated in order.</span></span> <span data-ttu-id="bc59b-311">前のほうの分岐で後ろにあるいずれかの case が処理されるようにパターンを並べ替えると、コンパイラによって到達できないコードに関する警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-311">If you rearrange them so that an earlier branch handles one of your later cases, the compiler warns you about the unreachable code.</span></span> <span data-ttu-id="bc59b-312">これらの言語ルールによって、コードが変化しないという自信を持って、前述した簡略化を簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-312">Those language rules made it easier to do the preceding simplifications with confidence that the code didn't change.</span></span>

<span data-ttu-id="bc59b-313">パターン マッチングによって、ある種のコードが読みやすくなり、クラスにコードを追加できない場合はオブジェクト指向の手法の代替として機能します。</span><span class="sxs-lookup"><span data-stu-id="bc59b-313">Pattern matching makes some types of code more readable and offers an alternative to object-oriented techniques when you can't add code to your classes.</span></span> <span data-ttu-id="bc59b-314">クラウドによって、データと機能は分離されています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-314">The cloud is causing data and functionality to live apart.</span></span> <span data-ttu-id="bc59b-315">データの "*形状*" とデータに対する "*操作*" は、必ずしも一緒に記述されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="bc59b-315">The *shape* of the data and the *operations* on it aren't necessarily described together.</span></span> <span data-ttu-id="bc59b-316">このチュートリアルでは、既存のデータを、元の関数とは完全に異なる方法で使用しています。</span><span class="sxs-lookup"><span data-stu-id="bc59b-316">In this tutorial, you consumed existing data in entirely different ways from its original function.</span></span> <span data-ttu-id="bc59b-317">パターン マッチングでは、型を拡張できない場合でも、それらをオーバーライドする機能を記述できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-317">Pattern matching gave you the ability to write functionality that overrode those types, even though you couldn't extend them.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc59b-318">次の手順</span><span class="sxs-lookup"><span data-stu-id="bc59b-318">Next steps</span></span>

<span data-ttu-id="bc59b-319">GitHub リポジトリの [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) から、完成したコードをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-319">You can download the finished code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) GitHub repository.</span></span> <span data-ttu-id="bc59b-320">自分のパターンを調査し、通常のコーディング アクティビティにこの手法を追加してください。</span><span class="sxs-lookup"><span data-stu-id="bc59b-320">Explore patterns on your own and add this technique into your regular coding activities.</span></span> <span data-ttu-id="bc59b-321">これらの手法を習得することで、別の方法で問題にアプローチし、新しい機能を作成できます。</span><span class="sxs-lookup"><span data-stu-id="bc59b-321">Learning these techniques gives you another way to approach problems and create new functionality.</span></span>
