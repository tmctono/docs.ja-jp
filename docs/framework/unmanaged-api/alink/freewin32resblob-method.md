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
ms.openlocfilehash: ea0fbceb1e778a2f26e0625a337b803f417b59eb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777249"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="91dc1-102">FreeWin32ResBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="91dc1-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="91dc1-103">Win32 リソース blob と関連付けられているリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="91dc1-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91dc1-104">構文</span><span class="sxs-lookup"><span data-stu-id="91dc1-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="91dc1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91dc1-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="91dc1-106">解放されるリソース blob。</span><span class="sxs-lookup"><span data-stu-id="91dc1-106">The resource blob to be released.</span></span> <span data-ttu-id="91dc1-107">このメソッドは、blob ポインターを NULL に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="91dc1-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91dc1-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="91dc1-108">Return Value</span></span>  
 <span data-ttu-id="91dc1-109">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="91dc1-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91dc1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="91dc1-110">Requirements</span></span>  
 <span data-ttu-id="91dc1-111">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="91dc1-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91dc1-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="91dc1-112">See also</span></span>

- [<span data-ttu-id="91dc1-113">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="91dc1-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="91dc1-114">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="91dc1-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="91dc1-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="91dc1-115">ALink API</span></span>](index.md)
