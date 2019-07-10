---
title: IBindingDisplay::InitializeForProcess メソッド
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c19b49e9e9d4e388706a96ff54d588d5aeff99b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775946"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="c44d4-102">IBindingDisplay::InitializeForProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="c44d4-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="c44d4-103">初期化します、 [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c44d4-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c44d4-104">構文</span><span class="sxs-lookup"><span data-stu-id="c44d4-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c44d4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c44d4-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="c44d4-106">[in]プロセス識別子。</span><span class="sxs-lookup"><span data-stu-id="c44d4-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c44d4-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="c44d4-107">Remarks</span></span>  
 <span data-ttu-id="c44d4-108">デバッガーの呼び出し、`InitializeForProcess`バインディングの表示を初期化するためには、作成時のメソッド。</span><span class="sxs-lookup"><span data-stu-id="c44d4-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="c44d4-109">`InitializeForProcess` その他のメソッドの前に、作成時に呼び出す必要があります`IBindingDisplay`が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c44d4-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c44d4-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="c44d4-110">Requirements</span></span>  
 <span data-ttu-id="c44d4-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c44d4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c44d4-112">**ヘッダー:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="c44d4-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="c44d4-113">**ライブラリ:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="c44d4-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="c44d4-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c44d4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44d4-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c44d4-115">See also</span></span>

- [<span data-ttu-id="c44d4-116">IBindingDisplay インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c44d4-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
