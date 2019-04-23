---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod メソッド
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4599d41336778db8ce8dcf3ac567e4e2cc8833e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174942"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="d9c3e-102">ISymUnmanagedAsyncMethod::GetKickoffMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="d9c3e-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="d9c3e-103">参照してください[DefineKickoffMethod メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="d9c3e-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9c3e-104">構文</span><span class="sxs-lookup"><span data-stu-id="d9c3e-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9c3e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d9c3e-105">Parameters</span></span>  
  
|<span data-ttu-id="d9c3e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d9c3e-106">Parameter</span></span>|<span data-ttu-id="d9c3e-107">説明</span><span class="sxs-lookup"><span data-stu-id="d9c3e-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="d9c3e-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="d9c3e-108">Return Value</span></span>  
 <span data-ttu-id="d9c3e-109">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="d9c3e-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9c3e-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="d9c3e-110">Requirements</span></span>  
 <span data-ttu-id="d9c3e-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d9c3e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9c3e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9c3e-112">See also</span></span>

- [<span data-ttu-id="d9c3e-113">ISymUnmanagedAsyncMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9c3e-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
