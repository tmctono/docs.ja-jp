---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod メソッド
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
ms.openlocfilehash: 879b9eac7cb6df06ffe4f994b505ea9cb2396d7f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441839"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="8c382-102">ISymUnmanagedAsyncMethod::GetKickoffMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="8c382-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="8c382-103">「 [DefineKickoffMethod メソッド](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c382-103">See [DefineKickoffMethod Method](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c382-104">構文</span><span class="sxs-lookup"><span data-stu-id="8c382-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c382-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c382-105">Parameters</span></span>  
  
|<span data-ttu-id="8c382-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c382-106">Parameter</span></span>|<span data-ttu-id="8c382-107">説明</span><span class="sxs-lookup"><span data-stu-id="8c382-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="8c382-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="8c382-108">Return Value</span></span>  
 <span data-ttu-id="8c382-109">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="8c382-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c382-110">要件</span><span class="sxs-lookup"><span data-stu-id="8c382-110">Requirements</span></span>  
 <span data-ttu-id="8c382-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="8c382-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c382-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c382-112">See also</span></span>

- [<span data-ttu-id="8c382-113">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c382-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
