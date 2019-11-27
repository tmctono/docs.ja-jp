---
title: EnumImportTypes メソッド
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
ms.openlocfilehash: ca7c7570aff63aa328dddc0626648fa74397addc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448736"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="028f3-102">EnumImportTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="028f3-102">EnumImportTypes Method</span></span>

<span data-ttu-id="028f3-103">各スコープ内の各型を列挙します。</span><span class="sxs-lookup"><span data-stu-id="028f3-103">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="028f3-104">構文</span><span class="sxs-lookup"><span data-stu-id="028f3-104">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="028f3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="028f3-105">Parameters</span></span>

`hEnum`\
<span data-ttu-id="028f3-106">列挙子のハンドル。</span><span class="sxs-lookup"><span data-stu-id="028f3-106">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="028f3-107">取得する型の最大数。</span><span class="sxs-lookup"><span data-stu-id="028f3-107">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="028f3-108">`dwMax`を超えないように、型トークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="028f3-108">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="028f3-109">`aTypeDefs`内の実際の型の数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="028f3-109">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="028f3-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="028f3-110">Return Value</span></span>

<span data-ttu-id="028f3-111">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="028f3-111">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="028f3-112">要件</span><span class="sxs-lookup"><span data-stu-id="028f3-112">Requirements</span></span>

<span data-ttu-id="028f3-113">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="028f3-113">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="028f3-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="028f3-114">See also</span></span>

- [<span data-ttu-id="028f3-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="028f3-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="028f3-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="028f3-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="028f3-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="028f3-117">ALink API</span></span>](index.md)
