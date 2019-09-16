---
title: 'チュートリアル: C# を使用してオブジェクトを永続化する'
ms.date: 04/26/2018
ms.openlocfilehash: 5e3a327ca0a257c45de361e0b3734e0b127f9869
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70851048"
---
# <a name="walkthrough-persisting-an-object-using-c"></a><span data-ttu-id="dbda5-102">チュートリアル: C\# を使用してオブジェクトを永続化する</span><span class="sxs-lookup"><span data-stu-id="dbda5-102">Walkthrough: persisting an object using C\#</span></span>

<span data-ttu-id="dbda5-103">シリアル化によってインスタンス間でオブジェクトのデータを永続化すると、値を保存しておき、次にそのオブジェクトをインスタンス化するときに、その値を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="dbda5-103">You can use serialization to persist an object's data between instances, which enables you to store values and retrieve them the next time that the object is instantiated.</span></span>

<span data-ttu-id="dbda5-104">このチュートリアルでは、基本的な `Loan` オブジェクトを作成し、そのデータをファイルに永続化します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-104">In this walkthrough, you will create a basic `Loan` object and persist its data to a file.</span></span> <span data-ttu-id="dbda5-105">その後、オブジェクトを再作成するときに、そのファイルからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-105">You will then retrieve the data from the file when you re-create the object.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbda5-106">次の例では、ファイルが存在しない場合は、新しいファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dbda5-106">This example creates a new file if the file does not already exist.</span></span> <span data-ttu-id="dbda5-107">アプリケーションでファイルを作成する必要がある場合、そのアプリケーションには、フォルダーに対する `Create` アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="dbda5-107">If an application must create a file, that application must have `Create` permission for the folder.</span></span> <span data-ttu-id="dbda5-108">アクセス許可は、アクセス制御リストを使用して設定します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-108">Permissions are set by using access control lists.</span></span> <span data-ttu-id="dbda5-109">ファイルが既に存在する場合、アプリケーションに必要なのは下位の `Write` アクセス許可だけです。</span><span class="sxs-lookup"><span data-stu-id="dbda5-109">If the file already exists, the application needs only `Write` permission, a lesser permission.</span></span> <span data-ttu-id="dbda5-110">可能な場合は、(フォルダーに対して Create アクセス許可を付与するのではなく) 配置時にファイルを作成し、1 つのファイルに対してのみ `Read` アクセス許可を付与する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="dbda5-110">Where possible, it's more secure to create the file during deployment and only grant `Read` permissions to a single file (instead of Create permissions for a folder).</span></span> <span data-ttu-id="dbda5-111">また、ルート フォルダーや Program Files フォルダーにデータを書き込むより、ユーザー フォルダーに書き込む方が安全です。</span><span class="sxs-lookup"><span data-stu-id="dbda5-111">Also, it's more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbda5-112">この例では、バイナリ形式のファイルにデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-112">This example stores data in a binary format file.</span></span> <span data-ttu-id="dbda5-113">この形式は、パスワードやクレジット カード情報などの重要情報には使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="dbda5-113">These formats should not be used for sensitive data, such as passwords or credit-card information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dbda5-114">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dbda5-114">Prerequisites</span></span>

- <span data-ttu-id="dbda5-115">ビルドして実行するには、[.NET Core SDK](https://dotnet.microsoft.com/download) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="dbda5-115">To build and run, install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

- <span data-ttu-id="dbda5-116">コード エディターをまだインストールしていなければ、お気に入りのエディターをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="dbda5-116">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="dbda5-117">コード エディターをインストールする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="dbda5-117">Need to install a code editor?</span></span> <span data-ttu-id="dbda5-118">[Visual Studio](https://visualstudio.com/downloads) をお試しください。</span><span class="sxs-lookup"><span data-stu-id="dbda5-118">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

- <span data-ttu-id="dbda5-119">この例では C# 7.3 が必要です。</span><span class="sxs-lookup"><span data-stu-id="dbda5-119">The example requires C# 7.3.</span></span> <span data-ttu-id="dbda5-120">「[C# 言語のバージョンの選択](../../../language-reference/configure-language-version.md)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="dbda5-120">See [Select the C# language version](../../../language-reference/configure-language-version.md)</span></span> 

<span data-ttu-id="dbda5-121">オンラインで [.NET サンプルの GitHub リポジトリ](https://github.com/dotnet/samples/tree/master/csharp/serialization)にアクセスしてサンプル コードを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="dbda5-121">You can examine the sample code online [at the .NET samples GitHub repository](https://github.com/dotnet/samples/tree/master/csharp/serialization).</span></span>

## <a name="creating-the-loan-object"></a><span data-ttu-id="dbda5-122">loan オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="dbda5-122">Creating the loan object</span></span>

<span data-ttu-id="dbda5-123">まず、`Loan` クラスとそのクラスを使用するコンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-123">The first step is to create a `Loan` class and a console application that uses the class:</span></span>

1. <span data-ttu-id="dbda5-124">新しいアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-124">Create a new application.</span></span> <span data-ttu-id="dbda5-125">「`dotnet new console -o serialization`」と入力して `serialization`という名前のサブディレクトリに新しいコンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-125">Type `dotnet new console -o serialization` to create a new console application in a subdirectory named `serialization`.</span></span>
1. <span data-ttu-id="dbda5-126">エディターでアプリケーションを開き、`Loan.cs` という名前の新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-126">Open the application in your editor, and add a new class named `Loan.cs`.</span></span>
1. <span data-ttu-id="dbda5-127">`Loan` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-127">Add the following code to your `Loan` class:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/csharp/serialization/Loan.cs#1)]

<span data-ttu-id="dbda5-128">また、`Loan` クラスを使用するアプリケーションも作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbda5-128">You will also have to create an application that uses the `Loan` class.</span></span>

## <a name="serialize-the-loan-object"></a><span data-ttu-id="dbda5-129">loan オブジェクトをシリアル化する</span><span class="sxs-lookup"><span data-stu-id="dbda5-129">Serialize the loan object</span></span>

1. <span data-ttu-id="dbda5-130">`Program.cs`を開きます。</span><span class="sxs-lookup"><span data-stu-id="dbda5-130">Open `Program.cs`.</span></span> <span data-ttu-id="dbda5-131">次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-131">Add the following code:</span></span>

[!code-csharp[Create a loan object](../../../../../samples/csharp/serialization/Program.cs#1)]

<span data-ttu-id="dbda5-132">`PropertyChanged` イベントのイベント ハンドラーを追加し、`Loan` オブジェクトを変更して変更を表示する処理を行う数行を追加します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-132">Add an event handler for the `PropertyChanged` event, and a few lines to modify the `Loan` object and display the changes.</span></span> <span data-ttu-id="dbda5-133">この追加は次のコードで確認できます。</span><span class="sxs-lookup"><span data-stu-id="dbda5-133">You can see the additions in the following code:</span></span>

[!code-csharp[Listening for the PropertyChanged event](../../../../../samples/csharp/serialization/Program.cs#2)]

<span data-ttu-id="dbda5-134">この時点で、コードを実行して現在の出力を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="dbda5-134">At this point, you can run the code, and see the current output:</span></span>

```console
New customer value: Henry Clay
7.5
7.1
```

<span data-ttu-id="dbda5-135">このアプリケーションを繰り返し実行すると、常に同じ値が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="dbda5-135">Running this application repeatedly always writes the same values.</span></span> <span data-ttu-id="dbda5-136">プログラムを実行するたびに新しい Loan オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dbda5-136">A new Loan object is created every time you run the program.</span></span> <span data-ttu-id="dbda5-137">実際には利率は定期的に変わりますが、アプリケーションを実行するたびに変わるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="dbda5-137">In the real world, interest rates change periodically, but not necessarily every time that the application is run.</span></span> <span data-ttu-id="dbda5-138">シリアル化コードとは、アプリケーションのインスタンス間で最新の利率を保持することを意味します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-138">Serialization code means you preserve the most recent interest rate between instances of the application.</span></span> <span data-ttu-id="dbda5-139">次の手順では、Loan クラスにシリアル化を追加して、利率を保持できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dbda5-139">In the next step, you will do just that by adding serialization to the Loan class.</span></span>

## <a name="using-serialization-to-persist-the-object"></a><span data-ttu-id="dbda5-140">シリアル化を使用したオブジェクトの永続化</span><span class="sxs-lookup"><span data-stu-id="dbda5-140">Using Serialization to Persist the Object</span></span>

<span data-ttu-id="dbda5-141">Loan クラスの値を永続化するには、まず、クラスを `Serializable` 属性でマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbda5-141">In order to persist the values for the Loan class, you must first mark the class with the `Serializable` attribute.</span></span> <span data-ttu-id="dbda5-142">Loan クラス定義の上に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-142">Add the following code above the Loan class definition:</span></span>

[!code-csharp[Loan class definition](../../../../../samples/csharp/serialization/Loan.cs#2)]

<span data-ttu-id="dbda5-143"><xref:System.SerializableAttribute> は、クラス内のすべての要素がファイルに永続化できることをコンパイラに示します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-143">The <xref:System.SerializableAttribute> tells the compiler that everything in the class can be persisted to a file.</span></span> <span data-ttu-id="dbda5-144">`PropertyChanged` イベントは保存する必要があるオブジェクト グラフの一部を表していないので、シリアル化しないようにします。</span><span class="sxs-lookup"><span data-stu-id="dbda5-144">Because the `PropertyChanged` event does not represent part of the object graph that should be stored, it should not be serialized.</span></span> <span data-ttu-id="dbda5-145">シリアル化すると、そのイベントにアタッチされているすべてのオブジェクトがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="dbda5-145">Doing so would serialize all objects that are attached to that event.</span></span> <span data-ttu-id="dbda5-146"><xref:System.NonSerializedAttribute> は、`PropertyChanged` イベント ハンドラーのフィールド宣言に追加できます。</span><span class="sxs-lookup"><span data-stu-id="dbda5-146">You can add the <xref:System.NonSerializedAttribute> to the field declaration for the `PropertyChanged` event handler.</span></span>

[!code-csharp[Disable serialization for the event handler](../../../../../samples/csharp/serialization/Loan.cs#3)]

<span data-ttu-id="dbda5-147">C# 7.3 以降、`field` のターゲット値を使用して、自動実装プロパティのバッキング フィールドに属性をアタッチできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="dbda5-147">Beginning with C# 7.3, you can attach attributes to the backing field of an auto-implemented property using the `field` target value.</span></span> <span data-ttu-id="dbda5-148">次のコードでは `TimeLastLoaded` プロパティを追加し、シリアル化可能ではないとマークします。</span><span class="sxs-lookup"><span data-stu-id="dbda5-148">The following code adds a `TimeLastLoaded` property and marks it as not serializable:</span></span>

[!code-csharp[Disable serialization for an auto-implemented property](../../../../../samples/csharp/serialization/Loan.cs#4)]

<span data-ttu-id="dbda5-149">次に、LoanApp アプリケーションにシリアル化コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-149">The next step is to add the serialization code to the LoanApp application.</span></span> <span data-ttu-id="dbda5-150">クラスをシリアル化してファイルに書き込むには、<xref:System.IO> 名前空間と <xref:System.Runtime.Serialization.Formatters.Binary> 名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-150">In order to serialize the class and write it to a file, you use the <xref:System.IO> and <xref:System.Runtime.Serialization.Formatters.Binary> namespaces.</span></span> <span data-ttu-id="dbda5-151">次のコードのように、必要な名前空間への参照を追加すると、完全修飾名の入力が不要になります。</span><span class="sxs-lookup"><span data-stu-id="dbda5-151">To avoid typing the fully qualified names, you can add references to the necessary namespaces as shown in the following code:</span></span>

[!code-csharp[Adding namespaces for serialization](../../../../../samples/csharp/serialization/Program.cs#3)]

<span data-ttu-id="dbda5-152">次の手順では、オブジェクトの作成時にファイルからオブジェクトを逆シリアル化するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-152">The next step is to add code to deserialize the object from the file when the object is created.</span></span> <span data-ttu-id="dbda5-153">次のコードのように、シリアル化されたデータのファイル名を定数としてクラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-153">Add a constant to the class for the serialized data's file name as shown in the following code:</span></span>

[!code-csharp[Define the name of the saved file](../../../../../samples/csharp/serialization/Program.cs#4)]

<span data-ttu-id="dbda5-154">次に、`TestLoan` オブジェクトを作成する行の後に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-154">Next, add the following code after the line that creates the `TestLoan` object:</span></span>

[!code-csharp[Read from a file if it exists](../../../../../samples/csharp/serialization/Program.cs#5)]

<span data-ttu-id="dbda5-155">まず、ファイルが存在することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbda5-155">You first must check that the file exists.</span></span> <span data-ttu-id="dbda5-156">ファイルが存在する場合は、バイナリ ファイルを読み取る <xref:System.IO.Stream> クラスと、ファイルを変換する <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-156">If it exists, create a <xref:System.IO.Stream> class to read the binary file and a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> class to translate the file.</span></span> <span data-ttu-id="dbda5-157">ストリーム型を Loan オブジェクト型に変換する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="dbda5-157">You also need to convert from the stream type to the Loan object type.</span></span>

<span data-ttu-id="dbda5-158">次に、クラスをファイルにシリアル化するコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbda5-158">Next you must add code to serialize the class to a file.</span></span> <span data-ttu-id="dbda5-159">`Main` メソッドの既存のコードの後に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-159">Add the following code after the existing code in the `Main` method:</span></span>

[!code-csharp[Save the existing Loan object](../../../../../samples/csharp/serialization/Program.cs#6)]

<span data-ttu-id="dbda5-160">この時点で、アプリケーションを再度ビルドして実行できます。</span><span class="sxs-lookup"><span data-stu-id="dbda5-160">At this point, you can again build and run the application.</span></span> <span data-ttu-id="dbda5-161">初めて実行すると、利率は 7.5 から始まり、7.1 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="dbda5-161">The first time it runs, notice that the interest rates starts at 7.5, and then changes to 7.1.</span></span> <span data-ttu-id="dbda5-162">いったんアプリケーションを閉じて、再び実行します。</span><span class="sxs-lookup"><span data-stu-id="dbda5-162">Close the application and then run it again.</span></span> <span data-ttu-id="dbda5-163">利率を変更するコードの前でも、保存済みのファイルが読み込まれ、利率は 7.1 であるというメッセージがアプリケーションから出力されます。</span><span class="sxs-lookup"><span data-stu-id="dbda5-163">Now, the application prints the message that it has read the saved file, and the interest rate is 7.1 even before the code that changes it.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbda5-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbda5-164">See also</span></span>

- [<span data-ttu-id="dbda5-165">シリアル化 (C#)</span><span class="sxs-lookup"><span data-stu-id="dbda5-165">Serialization (C#)</span></span>](index.md)
- [<span data-ttu-id="dbda5-166">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="dbda5-166">C# Programming Guide</span></span>](../..//index.md)
