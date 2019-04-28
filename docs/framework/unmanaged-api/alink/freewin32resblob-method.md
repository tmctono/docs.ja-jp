---
title: FreeWin32ResBlob メソッド
ms.date: 03/30/2017
api_name:
- IALink.FreeWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- FreeWin32ResBlob
helpviewer_keywords:
- FreeWin32ResBlob method
ms.assetid: d941102b-2679-4c49-b15e-c0fc9c53e11f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 196a57b3e919ea4ccbc0b91e5b6f281ad3c30b62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789884"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="39ca8-102">FreeWin32ResBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="39ca8-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="39ca8-103">Win32 リソースの blob と関連付けられているリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="39ca8-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39ca8-104">構文</span><span class="sxs-lookup"><span data-stu-id="39ca8-104">Syntax</span></span>  
  
```  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="39ca8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="39ca8-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="39ca8-106">解放されるリソースの blob。</span><span class="sxs-lookup"><span data-stu-id="39ca8-106">The resource blob to be released.</span></span> <span data-ttu-id="39ca8-107">このメソッドは、blob のポインターを NULL に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="39ca8-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39ca8-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="39ca8-108">Return Value</span></span>  
 <span data-ttu-id="39ca8-109">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="39ca8-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39ca8-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="39ca8-110">Requirements</span></span>  
 <span data-ttu-id="39ca8-111">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="39ca8-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39ca8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="39ca8-112">See also</span></span>

- [<span data-ttu-id="39ca8-113">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39ca8-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="39ca8-114">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39ca8-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="39ca8-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="39ca8-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
