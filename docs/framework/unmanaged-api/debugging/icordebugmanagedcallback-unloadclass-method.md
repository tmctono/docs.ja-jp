---
title: ICorDebugManagedCallback::UnloadClass メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
ms.openlocfilehash: a7b71170f58ddfe0295da28b8c9fc73286b074e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212270"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="c4fcd-102">ICorDebugManagedCallback::UnloadClass メソッド</span><span class="sxs-lookup"><span data-stu-id="c4fcd-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="c4fcd-103">クラスがアンロードされていることをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c4fcd-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4fcd-104">構文</span><span class="sxs-lookup"><span data-stu-id="c4fcd-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4fcd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c4fcd-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c4fcd-106">からクラスを含むアプリケーションドメインを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c4fcd-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="c4fcd-107">からクラスを表す、のオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c4fcd-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4fcd-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4fcd-108">Remarks</span></span>  
 <span data-ttu-id="c4fcd-109">この呼び出しの後にクラスを参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4fcd-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4fcd-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="c4fcd-110">Requirements</span></span>  
 <span data-ttu-id="c4fcd-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fcd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4fcd-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4fcd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4fcd-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4fcd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4fcd-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4fcd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4fcd-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4fcd-115">See also</span></span>

- [<span data-ttu-id="c4fcd-116">LoadClass メソッド</span><span class="sxs-lookup"><span data-stu-id="c4fcd-116">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="c4fcd-117">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c4fcd-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
