---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod メソッド
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce3c135e031d0c8425e990811fedc40f4ec45243
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226613"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="27c75-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod メソッド</span><span class="sxs-lookup"><span data-stu-id="27c75-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="27c75-103">非同期操作を開始する開始メソッドを設定します。</span><span class="sxs-lookup"><span data-stu-id="27c75-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27c75-104">構文</span><span class="sxs-lookup"><span data-stu-id="27c75-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27c75-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="27c75-105">Parameters</span></span>  
  
|<span data-ttu-id="27c75-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="27c75-106">Parameter</span></span>|<span data-ttu-id="27c75-107">説明</span><span class="sxs-lookup"><span data-stu-id="27c75-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="27c75-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="27c75-108">Return Value</span></span>  
 <span data-ttu-id="27c75-109">`HRESULT` を返します。</span><span class="sxs-lookup"><span data-stu-id="27c75-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27c75-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="27c75-110">Requirements</span></span>  
 <span data-ttu-id="27c75-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="27c75-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27c75-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="27c75-112">See also</span></span>

- [<span data-ttu-id="27c75-113">ISymUnmanagedAsyncMethodPropertiesWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27c75-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
