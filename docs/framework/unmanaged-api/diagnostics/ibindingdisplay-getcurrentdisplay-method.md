---
title: IBindingDisplay::GetCurrentDisplay メソッド
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d075aeeb904469613999829a1444511d069b9918
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775981"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="7cec5-102">IBindingDisplay::GetCurrentDisplay メソッド</span><span class="sxs-lookup"><span data-stu-id="7cec5-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="7cec5-103">現在のバインディングの表示情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7cec5-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cec5-104">構文</span><span class="sxs-lookup"><span data-stu-id="7cec5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cec5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7cec5-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="7cec5-106">[out, retval]バインドの表示情報を含む safearray へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7cec5-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cec5-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="7cec5-107">Remarks</span></span>  
 <span data-ttu-id="7cec5-108">[Ibindingdisplay::initializeforprocess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)メソッドが以前に成功しましたが、デバッガーでプログラムを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cec5-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="7cec5-109">呼び出し元の返される割り当てを解除する必要があります`SAFEARRAY`を使用してメモリ[SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)します。</span><span class="sxs-lookup"><span data-stu-id="7cec5-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cec5-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="7cec5-110">Requirements</span></span>  
 <span data-ttu-id="7cec5-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cec5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cec5-112">**ヘッダー:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="7cec5-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="7cec5-113">**ライブラリ:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="7cec5-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="7cec5-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cec5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cec5-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cec5-115">See also</span></span>

- [<span data-ttu-id="7cec5-116">IBindingDisplay インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7cec5-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [<span data-ttu-id="7cec5-117">InitializeForProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="7cec5-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
