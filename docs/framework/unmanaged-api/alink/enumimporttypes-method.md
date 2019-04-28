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
ms.openlocfilehash: 1d0aefea7345bc3bf37bdb8d13cb2cda19cfe527
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789956"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="5ea77-102">EnumImportTypes メソッド</span><span class="sxs-lookup"><span data-stu-id="5ea77-102">EnumImportTypes Method</span></span>

<span data-ttu-id="5ea77-103">それぞれのスコープでは、各種類を列挙します。</span><span class="sxs-lookup"><span data-stu-id="5ea77-103">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ea77-104">構文</span><span class="sxs-lookup"><span data-stu-id="5ea77-104">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="5ea77-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ea77-105">Parameters</span></span>

`hEnum`\
<span data-ttu-id="5ea77-106">列挙子の処理です。</span><span class="sxs-lookup"><span data-stu-id="5ea77-106">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="5ea77-107">取得する型の最大数。</span><span class="sxs-lookup"><span data-stu-id="5ea77-107">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="5ea77-108">超えないように、型のトークンを受け取る`dwMax`します。</span><span class="sxs-lookup"><span data-stu-id="5ea77-108">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="5ea77-109">型の実際の数を受け取る`aTypeDefs`します。</span><span class="sxs-lookup"><span data-stu-id="5ea77-109">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="5ea77-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="5ea77-110">Return Value</span></span>

<span data-ttu-id="5ea77-111">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="5ea77-111">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="5ea77-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="5ea77-112">Requirements</span></span>

<span data-ttu-id="5ea77-113">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="5ea77-113">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="5ea77-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ea77-114">See also</span></span>

- [<span data-ttu-id="5ea77-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ea77-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5ea77-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ea77-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5ea77-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="5ea77-117">ALink API</span></span>](index.md)