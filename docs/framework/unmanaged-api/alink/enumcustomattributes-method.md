---
title: EnumCustomAttributes メソッド
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
ms.openlocfilehash: 6a5b3f1e9bf1444feb73949ef7133fbd9ae35134
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446472"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="46671-102">EnumCustomAttributes メソッド</span><span class="sxs-lookup"><span data-stu-id="46671-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="46671-103">アセンブリレベルのカスタム属性を取得します。</span><span class="sxs-lookup"><span data-stu-id="46671-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46671-104">構文</span><span class="sxs-lookup"><span data-stu-id="46671-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="46671-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="46671-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="46671-106">列挙子のハンドル。</span><span class="sxs-lookup"><span data-stu-id="46671-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="46671-107">列挙する属性の型。</span><span class="sxs-lookup"><span data-stu-id="46671-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="46671-108">すべての属性には `mdTokenNill` を使用します。</span><span class="sxs-lookup"><span data-stu-id="46671-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="46671-109">カスタム属性トークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="46671-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="46671-110">`rCustomValues` 配列のサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="46671-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="46671-111">必要に応じて、トークンの値の数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="46671-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46671-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="46671-112">Return Value</span></span>  
 <span data-ttu-id="46671-113">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="46671-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46671-114">要件</span><span class="sxs-lookup"><span data-stu-id="46671-114">Requirements</span></span>  
 <span data-ttu-id="46671-115">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="46671-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46671-116">参照</span><span class="sxs-lookup"><span data-stu-id="46671-116">See also</span></span>

- [<span data-ttu-id="46671-117">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="46671-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="46671-118">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="46671-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="46671-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="46671-119">ALink API</span></span>](index.md)
