---
title: さまざまな型の配列のマーシャリング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fadccdf35429babce6e101d336c9ea1de150b276
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648607"
---
# <a name="marshaling-different-types-of-arrays"></a><span data-ttu-id="4ae3f-102">さまざまな型の配列のマーシャリング</span><span class="sxs-lookup"><span data-stu-id="4ae3f-102">Marshaling Different Types of Arrays</span></span>
<span data-ttu-id="4ae3f-103">配列は、同じ型の 1 つ以上の要素を含むマネージド コード内の参照型です。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-103">An array is a reference type in managed code that contains one or more elements of the same type.</span></span> <span data-ttu-id="4ae3f-104">配列は参照型ですが、アンマネージ関数には In パラメーターとして渡されます。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-104">Although arrays are reference types, they are passed as In parameters to unmanaged functions.</span></span> <span data-ttu-id="4ae3f-105">この動作は、マネージド配列がマネージド オブジェクトに渡される方法 (In/Out パラメーターとして渡される) と一致しません。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-105">This behavior is inconsistent with way managed arrays are passed to managed objects, which is as In/Out parameters.</span></span> <span data-ttu-id="4ae3f-106">詳細については、「 [コピーと固定](copying-and-pinning.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-106">For additional details, see [Copying and Pinning](copying-and-pinning.md).</span></span>  
  
 <span data-ttu-id="4ae3f-107">次の表では、配列のマーシャリング オプションをリストして、それらの使用方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-107">The following table lists marshaling options for arrays and describes their usage.</span></span>  
  
|<span data-ttu-id="4ae3f-108">配列</span><span class="sxs-lookup"><span data-stu-id="4ae3f-108">Array</span></span>|<span data-ttu-id="4ae3f-109">説明</span><span class="sxs-lookup"><span data-stu-id="4ae3f-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4ae3f-110">値による整数の。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-110">Of integers by value.</span></span>|<span data-ttu-id="4ae3f-111">整数の配列を In パラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-111">Passes an array of integers as an In parameter.</span></span>|  
|<span data-ttu-id="4ae3f-112">参照による整数の。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-112">Of integers by reference.</span></span>|<span data-ttu-id="4ae3f-113">整数の配列を In/Out パラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-113">Passes an array of integers as an In/Out parameter.</span></span>|  
|<span data-ttu-id="4ae3f-114">値による整数の (2 次元)。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-114">Of integers by value (two-dimensional).</span></span>|<span data-ttu-id="4ae3f-115">整数のマトリックスを In パラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-115">Passes a matrix of integers as an In parameter.</span></span>|  
|<span data-ttu-id="4ae3f-116">値による文字列の。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-116">Of strings by value.</span></span>|<span data-ttu-id="4ae3f-117">文字列の配列を In パラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-117">Passes an array of strings as an In parameter.</span></span>|  
|<span data-ttu-id="4ae3f-118">整数による構造体の。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-118">Of structures with integers.</span></span>|<span data-ttu-id="4ae3f-119">In パラメーターとして整数を含む構造体の配列を渡します。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-119">Passes an array of structures that contain integers as an In parameter.</span></span>|  
|<span data-ttu-id="4ae3f-120">文字列による構造体の。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-120">Of structures with strings.</span></span>|<span data-ttu-id="4ae3f-121">In/Out パラメーターとして文字列のみを含む構造体の配列を渡します。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-121">Passes an array of structures that contain only strings as an In/Out parameter.</span></span> <span data-ttu-id="4ae3f-122">配列のメンバーを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-122">Members of the array can be changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4ae3f-123">例</span><span class="sxs-lookup"><span data-stu-id="4ae3f-123">Example</span></span>  
 <span data-ttu-id="4ae3f-124">このサンプルは、以下の種類の配列差を渡す法を示します。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-124">This sample demonstrates how to pass the following types of arrays:</span></span>  
  
- <span data-ttu-id="4ae3f-125">値による整数の配列。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-125">Array of integers by value.</span></span>  
  
- <span data-ttu-id="4ae3f-126">サイズを変更できる、参照による整数の配列。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-126">Array of integers by reference, which can be resized.</span></span>  
  
- <span data-ttu-id="4ae3f-127">値による整数の多次元配列 (マトリックス)。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-127">Multidimensional array (matrix) of integers by value.</span></span>  
  
- <span data-ttu-id="4ae3f-128">値による文字列の配列。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-128">Array of strings by value.</span></span>  
  
- <span data-ttu-id="4ae3f-129">整数による構造体の配列。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-129">Array of structures with integers.</span></span>  
  
- <span data-ttu-id="4ae3f-130">文字列による構造体の配列。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-130">Array of structures with strings.</span></span>  
  
 <span data-ttu-id="4ae3f-131">配列が参照によって明示的にマーシャリングされない限り、既定の動作は、配列を In パラメーターとしてマーシャリングすることです。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-131">Unless an array is explicitly marshaled by reference, the default behavior marshals the array as an In parameter.</span></span> <span data-ttu-id="4ae3f-132">この動作は、 <xref:System.Runtime.InteropServices.InAttribute> と <xref:System.Runtime.InteropServices.OutAttribute> 属性を明示的に適用することで変更できます。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-132">You can change this behavior by applying the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes explicitly.</span></span>  
  
 <span data-ttu-id="4ae3f-133">Arrays のサンプルで使用するアンマネージ関数とその元の関数宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-133">The Arrays sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
- <span data-ttu-id="4ae3f-134">PinvokeLib.dll からエクスポートされる**TestArrayOfInts** 。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-134">**TestArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
- <span data-ttu-id="4ae3f-135">PinvokeLib.dll からエクスポートされる**TestRefArrayOfInts** 。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-135">**TestRefArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
- <span data-ttu-id="4ae3f-136">PinvokeLib.dll からエクスポートされる**TestMatrixOfInts** 。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-136">**TestMatrixOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
- <span data-ttu-id="4ae3f-137">PinvokeLib.dll からエクスポートされる**TestArrayOfStrings** 。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-137">**TestArrayOfStrings** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
- <span data-ttu-id="4ae3f-138">PinvokeLib.dll からエクスポートされる**TestArrayOfStructs** 。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-138">**TestArrayOfStructs** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
- <span data-ttu-id="4ae3f-139">PinvokeLib.dll からエクスポートされる**TestArrayOfStructs2** 。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-139">**TestArrayOfStructs2** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 <span data-ttu-id="4ae3f-140">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) はカスタム アンマネージ ライブラリであり、上記の関数および 2 つの構造体変数 **MYPOINT** および **MYPERSON**に関する実装を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-140">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and two structure variables, **MYPOINT** and **MYPERSON**.</span></span> <span data-ttu-id="4ae3f-141">構造体には次の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-141">The structures contain the following elements:</span></span>  
  
```  
typedef struct _MYPOINT  
{  
   int x;   
   int y;   
} MYPOINT;  
  
typedef struct _MYPERSON  
{  
   char* first;   
   char* last;   
} MYPERSON;  
```  
  
 <span data-ttu-id="4ae3f-142">このサンプルでは、 `MyPoint` と `MyPerson` 構造体に埋め込み型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-142">In this sample, the `MyPoint` and `MyPerson` structures contain embedded types.</span></span> <span data-ttu-id="4ae3f-143">各メンバーが出現する順番でメモリ内に順次配列されることを保証するために、 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-143">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="4ae3f-144">`LibWrap` クラスには、 `App` クラスによって呼び出されるメソッドのセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-144">The `LibWrap` class contains a set of methods called by the `App` class.</span></span> <span data-ttu-id="4ae3f-145">配列を渡す特定の方法について詳しくは、次のサンプル内のコメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-145">For specific details about passing arrays, see the comments in the following sample.</span></span> <span data-ttu-id="4ae3f-146">参照型の配列は、既定では In パラメーターとして渡されます。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-146">An array, which is a reference type, is passed as an In parameter by default.</span></span> <span data-ttu-id="4ae3f-147">呼び出し元が結果を受け取るためには、 **InAttribute** と **OutAttribute** を配列が含まれる引数に明示的に適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ae3f-147">For the caller to receive the results, **InAttribute** and **OutAttribute** must be applied explicitly to the argument containing the array.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="4ae3f-148">プロトタイプの宣言</span><span class="sxs-lookup"><span data-stu-id="4ae3f-148">Declaring Prototypes</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a><span data-ttu-id="4ae3f-149">関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="4ae3f-149">Calling Functions</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="4ae3f-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ae3f-150">See also</span></span>

- [<span data-ttu-id="4ae3f-151">プラットフォーム呼び出しのデータ型</span><span class="sxs-lookup"><span data-stu-id="4ae3f-151">Platform invoke data types</span></span>](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [<span data-ttu-id="4ae3f-152">マネージド コードでのプロトタイプの作成</span><span class="sxs-lookup"><span data-stu-id="4ae3f-152">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
