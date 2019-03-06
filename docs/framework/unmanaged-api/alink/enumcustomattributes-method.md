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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e351c61f7e8bfc254a6fc8ea12c8a94fc393e3fc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478155"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="d21a1-102">EnumCustomAttributes メソッド</span><span class="sxs-lookup"><span data-stu-id="d21a1-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="d21a1-103">アセンブリ レベルのカスタム属性を取得します。</span><span class="sxs-lookup"><span data-stu-id="d21a1-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d21a1-104">構文</span><span class="sxs-lookup"><span data-stu-id="d21a1-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d21a1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d21a1-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="d21a1-106">列挙子のハンドル。</span><span class="sxs-lookup"><span data-stu-id="d21a1-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="d21a1-107">列挙する属性の型。</span><span class="sxs-lookup"><span data-stu-id="d21a1-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="d21a1-108">使用`mdTokenNill`すべての属性。</span><span class="sxs-lookup"><span data-stu-id="d21a1-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="d21a1-109">カスタム属性のトークンを受信します。</span><span class="sxs-lookup"><span data-stu-id="d21a1-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d21a1-110">サイズを指定`rCustomValues`配列。</span><span class="sxs-lookup"><span data-stu-id="d21a1-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="d21a1-111">必要に応じてトークンの値の数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d21a1-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d21a1-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="d21a1-112">Return Value</span></span>  
 <span data-ttu-id="d21a1-113">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="d21a1-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d21a1-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="d21a1-114">Requirements</span></span>  
 <span data-ttu-id="d21a1-115">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="d21a1-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d21a1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d21a1-116">See also</span></span>
- [<span data-ttu-id="d21a1-117">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d21a1-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d21a1-118">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d21a1-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d21a1-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="d21a1-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
