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
ms.openlocfilehash: db2474741012c4fd1734adafed112821c42c099c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541709"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="5aefa-102">IBindingDisplay::GetCurrentDisplay メソッド</span><span class="sxs-lookup"><span data-stu-id="5aefa-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="5aefa-103">現在のバインディング表示情報を返します。</span><span class="sxs-lookup"><span data-stu-id="5aefa-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aefa-104">構文</span><span class="sxs-lookup"><span data-stu-id="5aefa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5aefa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5aefa-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="5aefa-106">[out, retval]バインディング表示情報を格納している safearray へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5aefa-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5aefa-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5aefa-107">Remarks</span></span>  
 <span data-ttu-id="5aefa-108">[IBindingDisplay:: InitializeForProcess](ibindingdisplay-initializeforprocess-method.md)メソッドが既に成功しており、プログラムがデバッガーによって停止されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aefa-108">The [IBindingDisplay::InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="5aefa-109">呼び出し元は、SafeArrayDestroy を使用して、返されたメモリの割り当てを解除する必要があり `SAFEARRAY` ます。 [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)</span><span class="sxs-lookup"><span data-stu-id="5aefa-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aefa-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="5aefa-110">Requirements</span></span>  
 <span data-ttu-id="5aefa-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aefa-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5aefa-112">**ヘッダー:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="5aefa-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="5aefa-113">**ライブラリ:** BindingDisplay .idl</span><span class="sxs-lookup"><span data-stu-id="5aefa-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="5aefa-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5aefa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aefa-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5aefa-115">See also</span></span>

- [<span data-ttu-id="5aefa-116">IBindingDisplay インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5aefa-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
- [<span data-ttu-id="5aefa-117">InitializeForProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="5aefa-117">InitializeForProcess Method</span></span>](ibindingdisplay-initializeforprocess-method.md)
