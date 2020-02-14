---
title: MemoryStream (System.IO) メソッド ()
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: d82b5080e9fbd5fc6603f1cddae996c75a06d3a3
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215461"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a><span data-ttu-id="b206c-102">MemoryStream および Length メソッド</span><span class="sxs-lookup"><span data-stu-id="b206c-102">MemoryStream.InternalGetOriginAndLength method</span></span>

<span data-ttu-id="b206c-103">メモリストリームの原点と長さの内部値を取得します。</span><span class="sxs-lookup"><span data-stu-id="b206c-103">Gets the internal values of origin and length of the memory stream.</span></span>

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a><span data-ttu-id="b206c-104">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b206c-104">Parameters</span></span>

- <span data-ttu-id="b206c-105">`origin` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="b206c-105">`origin` <xref:System.Int32></span></span>\
  <span data-ttu-id="b206c-106">このメソッドから制御が戻るときに、新しい <xref:System.IO.MemoryStream> オブジェクトを作成するときに指定されたバイト配列のオフセット。</span><span class="sxs-lookup"><span data-stu-id="b206c-106">When this method returns, the offset of the byte array specified when creating a new <xref:System.IO.MemoryStream> object.</span></span> <span data-ttu-id="b206c-107"><xref:System.IO.MemoryStream>によってバイト配列が作成された場合は0を格納します。</span><span class="sxs-lookup"><span data-stu-id="b206c-107">Contains 0 if the byte array was created by <xref:System.IO.MemoryStream>.</span></span>

- <span data-ttu-id="b206c-108">`length` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="b206c-108">`length` <xref:System.Int32></span></span>\
  <span data-ttu-id="b206c-109">このメソッドから制御が戻るときに、メモリストリーム内のバイト数。</span><span class="sxs-lookup"><span data-stu-id="b206c-109">When this method returns, the number of bytes within the memory stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="b206c-110">コメント</span><span class="sxs-lookup"><span data-stu-id="b206c-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="b206c-111">`MemoryStream.InternalGetOriginAndLength` メソッドは内部であり、コードで直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="b206c-111">The `MemoryStream.InternalGetOriginAndLength` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="b206c-112">Microsoft では、どのような状況でも、実稼働アプリケーションでこの方法を使用することはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b206c-112">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="b206c-113">要件</span><span class="sxs-lookup"><span data-stu-id="b206c-113">Requirements</span></span>

<span data-ttu-id="b206c-114">**名前空間:** <xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="b206c-114">**Namespace:** <xref:System.IO></span></span>

<span data-ttu-id="b206c-115">**アセンブリ:** mscorlib.dll (mscorlib.dll 内)</span><span class="sxs-lookup"><span data-stu-id="b206c-115">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="b206c-116">**.NET Framework のバージョン:** 2.0 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b206c-116">**.NET Framework versions:** Available since 2.0.</span></span>
