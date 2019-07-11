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
ms.openlocfilehash: 9b6c839cc664105149f26b0d21d7ba7fb91b3e29
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742203"
---
# <a name="closeenum-method"></a><span data-ttu-id="34057-102">CloseEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="34057-102">CloseEnum Method</span></span>
<span data-ttu-id="34057-103">指定の列挙体を終了し、関連付けられているリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="34057-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34057-104">構文</span><span class="sxs-lookup"><span data-stu-id="34057-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="34057-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34057-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="34057-106">終了する列挙体のハンドル。</span><span class="sxs-lookup"><span data-stu-id="34057-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34057-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="34057-107">Return Value</span></span>  
 <span data-ttu-id="34057-108">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="34057-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34057-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="34057-109">Requirements</span></span>  
 <span data-ttu-id="34057-110">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="34057-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34057-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="34057-111">See also</span></span>

- [<span data-ttu-id="34057-112">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34057-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="34057-113">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34057-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="34057-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="34057-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
