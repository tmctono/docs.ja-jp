---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod メソッド
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24560ed4b0bb7ca04d5859280baa594fbb2e4097
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473469"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="9ac49-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="9ac49-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="9ac49-103">非同期操作を開始する開始メソッドを設定します。</span><span class="sxs-lookup"><span data-stu-id="9ac49-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ac49-104">構文</span><span class="sxs-lookup"><span data-stu-id="9ac49-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ac49-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ac49-105">Parameters</span></span>  
  
|<span data-ttu-id="9ac49-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ac49-106">Parameter</span></span>|<span data-ttu-id="9ac49-107">説明</span><span class="sxs-lookup"><span data-stu-id="9ac49-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="9ac49-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="9ac49-108">Return Value</span></span>  
 <span data-ttu-id="9ac49-109">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="9ac49-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ac49-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="9ac49-110">Requirements</span></span>  
 <span data-ttu-id="9ac49-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9ac49-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac49-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ac49-112">See also</span></span>
- [<span data-ttu-id="9ac49-113">ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ac49-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
