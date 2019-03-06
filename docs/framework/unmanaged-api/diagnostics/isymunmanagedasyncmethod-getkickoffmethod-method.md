---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod メソッド
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84aef2b26e008d1a3c6d95d7ec1e130ab0594a11
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484551"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="2c6e1-102">ISymUnmanagedAsyncMethod::GetKickoffMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="2c6e1-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="2c6e1-103">参照してください[DefineKickoffMethod メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="2c6e1-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c6e1-104">構文</span><span class="sxs-lookup"><span data-stu-id="2c6e1-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c6e1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c6e1-105">Parameters</span></span>  
  
|<span data-ttu-id="2c6e1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c6e1-106">Parameter</span></span>|<span data-ttu-id="2c6e1-107">説明</span><span class="sxs-lookup"><span data-stu-id="2c6e1-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="2c6e1-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="2c6e1-108">Return Value</span></span>  
 <span data-ttu-id="2c6e1-109">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="2c6e1-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c6e1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="2c6e1-110">Requirements</span></span>  
 <span data-ttu-id="2c6e1-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2c6e1-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c6e1-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c6e1-112">See also</span></span>
- [<span data-ttu-id="2c6e1-113">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c6e1-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
