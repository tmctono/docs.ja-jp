---
title: ICorDebug::DebugActiveProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 2d71cebb77ed3ca586e857710667c0077f4f76ed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793578"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="146f5-102">ICorDebug::DebugActiveProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="146f5-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="146f5-103">デバッガーを既存のプロセスにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="146f5-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="146f5-104">構文</span><span class="sxs-lookup"><span data-stu-id="146f5-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="146f5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="146f5-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="146f5-106">からデバッガーがアタッチされるプロセスの ID。</span><span class="sxs-lookup"><span data-stu-id="146f5-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="146f5-107">からデバッガーがプロセスの Win32 デバッガーとして動作し、アンマネージコールバックをディスパッチする必要がある場合に `true` に設定されるブール値。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="146f5-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="146f5-108">入出力デバッガーがアタッチされているプロセスを表す "いいプロセス" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="146f5-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="146f5-109">コメント</span><span class="sxs-lookup"><span data-stu-id="146f5-109">Remarks</span></span>  
 <span data-ttu-id="146f5-110">相互運用デバッグは、IA-64 ベースおよび AMD64 ベースのプラットフォームなど、Win9x および x86 以外のプラットフォームではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="146f5-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="146f5-111">要件</span><span class="sxs-lookup"><span data-stu-id="146f5-111">Requirements</span></span>  
 <span data-ttu-id="146f5-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="146f5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="146f5-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="146f5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="146f5-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="146f5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="146f5-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="146f5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="146f5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="146f5-116">See also</span></span>

- [<span data-ttu-id="146f5-117">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="146f5-117">ICorDebug Interface</span></span>](icordebug-interface.md)
