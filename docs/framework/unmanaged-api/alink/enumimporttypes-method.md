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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cd154ac90418dd0f6f476151686ff670c01c98c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632232"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="3a0b0-102">EnumImportTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="3a0b0-102">EnumImportTypes Method</span></span>

<span data-ttu-id="3a0b0-103">それぞれのスコープでは、各種類を列挙します。</span><span class="sxs-lookup"><span data-stu-id="3a0b0-103">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="3a0b0-104">構文</span><span class="sxs-lookup"><span data-stu-id="3a0b0-104">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="3a0b0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a0b0-105">Parameters</span></span>

`hEnum`\
<span data-ttu-id="3a0b0-106">列挙子の処理です。</span><span class="sxs-lookup"><span data-stu-id="3a0b0-106">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="3a0b0-107">取得する型の最大数。</span><span class="sxs-lookup"><span data-stu-id="3a0b0-107">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="3a0b0-108">超えないように、型のトークンを受け取る`dwMax`します。</span><span class="sxs-lookup"><span data-stu-id="3a0b0-108">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="3a0b0-109">型の実際の数を受け取る`aTypeDefs`します。</span><span class="sxs-lookup"><span data-stu-id="3a0b0-109">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="3a0b0-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="3a0b0-110">Return Value</span></span>

<span data-ttu-id="3a0b0-111">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="3a0b0-111">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="3a0b0-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="3a0b0-112">Requirements</span></span>

<span data-ttu-id="3a0b0-113">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="3a0b0-113">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="3a0b0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a0b0-114">See also</span></span>

- [<span data-ttu-id="3a0b0-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a0b0-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3a0b0-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a0b0-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3a0b0-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="3a0b0-117">ALink API</span></span>](index.md)
