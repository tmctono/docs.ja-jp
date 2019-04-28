---
title: EndMerge メソッド
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 020cc56126249b27a52387e6efa3aa10c83d9126
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789988"
---
# <a name="endmerge-method"></a><span data-ttu-id="3414d-102">EndMerge メソッド</span><span class="sxs-lookup"><span data-stu-id="3414d-102">EndMerge Method</span></span>
<span data-ttu-id="3414d-103">すべてのカスタム属性が生成スコープにマージされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="3414d-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3414d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3414d-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3414d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3414d-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3414d-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="3414d-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3414d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3414d-107">Return Value</span></span>  
 <span data-ttu-id="3414d-108">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="3414d-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3414d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="3414d-109">Requirements</span></span>  
 <span data-ttu-id="3414d-110">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="3414d-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3414d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="3414d-111">See also</span></span>

- [<span data-ttu-id="3414d-112">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3414d-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3414d-113">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3414d-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3414d-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="3414d-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
