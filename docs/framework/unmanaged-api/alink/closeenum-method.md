---
title: CloseEnum メソッド
ms.date: 03/30/2017
api_name:
- CloseEnum
- IALink.CloseEnum
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseEnum
helpviewer_keywords:
- CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd7d63596690e2a5d0bc26448884ec09ecd63231
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129520"
---
# <a name="closeenum-method"></a><span data-ttu-id="9e1b2-102">CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="9e1b2-102">CloseEnum Method</span></span>
<span data-ttu-id="9e1b2-103">指定の列挙体を終了し、関連付けられているリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="9e1b2-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e1b2-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e1b2-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e1b2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9e1b2-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="9e1b2-106">終了する列挙体のハンドル。</span><span class="sxs-lookup"><span data-stu-id="9e1b2-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e1b2-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="9e1b2-107">Return Value</span></span>  
 <span data-ttu-id="9e1b2-108">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="9e1b2-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e1b2-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="9e1b2-109">Requirements</span></span>  
 <span data-ttu-id="9e1b2-110">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="9e1b2-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e1b2-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e1b2-111">See also</span></span>

- [<span data-ttu-id="9e1b2-112">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e1b2-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="9e1b2-113">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e1b2-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="9e1b2-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="9e1b2-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
