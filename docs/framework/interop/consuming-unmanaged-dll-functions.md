---
title: アンマネージ DLL 関数の処理
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- platform invoke, about platform invoke
- DLL functions, consuming unmanaged
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke
- DLL functions
ms.assetid: eca7606e-ebfb-4f47-b8d9-289903fdc045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e9308d6bf0eefaa60af17a721cd1c26827469eb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946846"
---
# <a name="consuming-unmanaged-dll-functions"></a><span data-ttu-id="1cdbf-102">アンマネージ DLL 関数の処理</span><span class="sxs-lookup"><span data-stu-id="1cdbf-102">Consuming Unmanaged DLL Functions</span></span>
<span data-ttu-id="1cdbf-103">プラットフォーム呼び出しは、マネージド コードがダイナミック リンク ライブラリ (DLL) に実装されたアンマネージド関数 (Windows API に含まれているものなど) を呼び出すことを可能にするサービスです。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-103">Platform invoke is a service that enables managed code to call unmanaged functions implemented in dynamic link libraries (DLLs), such as those in the Windows API.</span></span> <span data-ttu-id="1cdbf-104">これはエクスポートされた関数を見つけて呼び出し、必要に応じて相互運用の境界を越えて、その引数 (整数、文字列、配列、構造体、その他) をマーシャリングします。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-104">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="1cdbf-105">このセクションでは、アンマネージド DLL 関数の使用に関連するタスクを紹介し、プラットフォーム呼び出しについての詳しい情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-105">This section introduces tasks associated with consuming unmanaged DLL functions and provides more information about platform invoke.</span></span> <span data-ttu-id="1cdbf-106">以下のタスクに加えて、一般的な考慮事項、および追加情報や例を提供するリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-106">In addition to the following tasks, there are general considerations and a link providing additional information and examples.</span></span>  
  
#### <a name="to-consume-exported-dll-functions"></a><span data-ttu-id="1cdbf-107">エクスポートされた DLL 関数を使用するには</span><span class="sxs-lookup"><span data-stu-id="1cdbf-107">To consume exported DLL functions</span></span>  
  
1. <span data-ttu-id="1cdbf-108">[DLL 内の関数を識別します](../../../docs/framework/interop/identifying-functions-in-dlls.md)。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-108">[Identify functions in DLLs](../../../docs/framework/interop/identifying-functions-in-dlls.md).</span></span>  
  
     <span data-ttu-id="1cdbf-109">少なくとも、関数の名前とそれを含んでいる DLL の名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-109">Minimally, you must specify the name of the function and name of the DLL that contains it.</span></span>  
  
2. <span data-ttu-id="1cdbf-110">[DLL 関数を保持するクラスを作成します](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-110">[Create a class to hold DLL functions](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).</span></span>  
  
     <span data-ttu-id="1cdbf-111">既存のクラスを使用して、アンマネージ関数ごとに個別のクラスを作成するか、または関連するアンマネージ関数のセットを格納する 1 つのクラスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-111">You can use an existing class, create an individual class for each unmanaged function, or create one class that contains a set of related unmanaged functions.</span></span>  
  
3. <span data-ttu-id="1cdbf-112">[マネージド コードでプロトタイプを作成します](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-112">[Create prototypes in managed code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span></span>  
  
     <span data-ttu-id="1cdbf-113">[Visual Basic] **Declare** ステートメントを **Function** および **Lib** キーワードと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-113">[Visual Basic] Use the **Declare** statement with the **Function** and **Lib** keywords.</span></span> <span data-ttu-id="1cdbf-114">いくつかのまれなケースでは、**DllImportAttribute** を **Shared Function** キーワードと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-114">In some rare cases, you can use the **DllImportAttribute** with the **Shared Function** keywords.</span></span> <span data-ttu-id="1cdbf-115">それらのケースについては、このセクションで後述します。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-115">These cases are explained later in this section.</span></span>  
  
     <span data-ttu-id="1cdbf-116">[C#] **DllImportAttribute** を使用して DLL と関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-116">[C#] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="1cdbf-117">メソッドを **static** および **extern** 修飾子でマークします。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-117">Mark the method with the **static** and **extern** modifiers.</span></span>  
  
     <span data-ttu-id="1cdbf-118">[C++] **DllImportAttribute** を使用して DLL と関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-118">[C++] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="1cdbf-119">ラッパー メソッドまたは関数を **extern "C"** でマークします。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-119">Mark the wrapper method or function with **extern "C"**.</span></span>  
  
4. <span data-ttu-id="1cdbf-120">[DLL 関数を呼び出します](../../../docs/framework/interop/calling-a-dll-function.md)。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-120">[Call a DLL function](../../../docs/framework/interop/calling-a-dll-function.md).</span></span>  
  
     <span data-ttu-id="1cdbf-121">他のマネージド メソッドと同様の方法で、マネージド クラスのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-121">Call the method on your managed class as you would any other managed method.</span></span> <span data-ttu-id="1cdbf-122">[構造体の受け渡し](../../../docs/framework/interop/passing-structures.md)および[コールバック関数の実装](../../../docs/framework/interop/callback-functions.md)は、特殊なケースです。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-122">[Passing structures](../../../docs/framework/interop/passing-structures.md) and [implementing callback functions](../../../docs/framework/interop/callback-functions.md) are special cases.</span></span>  
  
 <span data-ttu-id="1cdbf-123">プラットフォーム呼び出しで使用する .NET ベースの宣言を作成する方法を示す例については、「[プラットフォーム呼び出しによるデータのマーシャリング](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-123">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="a-closer-look-at-platform-invoke"></a><span data-ttu-id="1cdbf-124">プラットフォーム呼び出しの詳細</span><span class="sxs-lookup"><span data-stu-id="1cdbf-124">A closer look at platform invoke</span></span>  
 <span data-ttu-id="1cdbf-125">プラットフォーム呼び出しは、エクスポート関数を検索して、その引数を実行時にマーシャリングするために、メタデータに依存します。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-125">Platform invoke relies on metadata to locate exported functions and marshal their arguments at run time.</span></span> <span data-ttu-id="1cdbf-126">次に、このプロセスの図を示します。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-126">The following illustration shows this process.</span></span>  
  
 ![プラットフォーム呼び出しを示す図。](./media/consuming-unmanaged-dll-functions/platform-invoke-call.gif)  
  
 <span data-ttu-id="1cdbf-128">プラットフォーム呼び出しがアンマネージ関数を呼び出すと、以下の一連のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-128">When platform invoke calls an unmanaged function, it performs the following sequence of actions:</span></span>  
  
1. <span data-ttu-id="1cdbf-129">関数を含む DLL を検索します。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-129">Locates the DLL containing the function.</span></span>  
  
2. <span data-ttu-id="1cdbf-130">DLL をメモリに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-130">Loads the DLL into memory.</span></span>  
  
3. <span data-ttu-id="1cdbf-131">メモリ内の関数のアドレスを検索し、その引数をスタックにプッシュし、必要に応じてデータをマーシャリングします。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-131">Locates the address of the function in memory and pushes its arguments onto the stack, marshaling data as required.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1cdbf-132">DLL の検索と読み込み、およびメモリ内の関数のアドレスの検索は、その関数を初めて呼び出したときにのみ生じます。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-132">Locating and loading the DLL, and locating the address of the function in memory occur only on the first call to the function.</span></span>  
  
4. <span data-ttu-id="1cdbf-133">アンマネージ関数に制御を移します。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-133">Transfers control to the unmanaged function.</span></span>  
  
 <span data-ttu-id="1cdbf-134">プラットフォーム呼び出しは、アンマネージド 関数によって生成された例外を、マネージド呼び出し元にスローします。</span><span class="sxs-lookup"><span data-stu-id="1cdbf-134">Platform invoke throws exceptions generated by the unmanaged function to the managed caller.</span></span>

## <a name="see-also"></a><span data-ttu-id="1cdbf-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cdbf-135">See also</span></span>

- [<span data-ttu-id="1cdbf-136">アンマネージ コードとの相互運用</span><span class="sxs-lookup"><span data-stu-id="1cdbf-136">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)
- [<span data-ttu-id="1cdbf-137">プラットフォーム呼び出しの例</span><span class="sxs-lookup"><span data-stu-id="1cdbf-137">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="1cdbf-138">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="1cdbf-138">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
