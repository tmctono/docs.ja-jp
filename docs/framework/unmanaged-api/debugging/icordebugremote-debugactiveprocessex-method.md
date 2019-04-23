---
title: ICorDebugRemote::DebugActiveProcessEx メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45b919d90454c9424cadb1d4dfc3b0dfb09e5053
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209451"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="a1173-102">ICorDebugRemote::DebugActiveProcessEx メソッド</span><span class="sxs-lookup"><span data-stu-id="a1173-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="a1173-103">デバッガーでのリモート コンピューター上のプロセスを起動します。</span><span class="sxs-lookup"><span data-stu-id="a1173-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1173-104">構文</span><span class="sxs-lookup"><span data-stu-id="a1173-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1173-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1173-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="a1173-106">[in]ポインター、 [ICorDebugRemoteTarget インターフェイス](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1173-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="a1173-107">このパラメーターを使用してをプロセスが実行されているコンピューターを特定します。</span><span class="sxs-lookup"><span data-stu-id="a1173-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="a1173-108">[in]デバッガーのアタッチ先のプロセスの ID。</span><span class="sxs-lookup"><span data-stu-id="a1173-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="a1173-109">[in]`true`デバッガーで、Win32 のデバッガー プロセスとして動作する必要があります、アンマネージのコールバックのディスパッチ場合それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="a1173-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="a1173-110">[out]デバッガーのアタッチするプロセスを表す"ICorDebugProcess"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a1173-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1173-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="a1173-111">Return Value</span></span>  
 <span data-ttu-id="a1173-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1173-112">S_OK</span></span>  
 <span data-ttu-id="a1173-113">リモート コンピューター上のプロセスに正常に接続します。</span><span class="sxs-lookup"><span data-stu-id="a1173-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="a1173-114">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="a1173-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="a1173-115">リモート コンピューター上のプロセスにアタッチできません。</span><span class="sxs-lookup"><span data-stu-id="a1173-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1173-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="a1173-116">Remarks</span></span>  
 <span data-ttu-id="a1173-117">Silverlight では、混合モード デバッグはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a1173-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1173-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1173-118">Requirements</span></span>  
 <span data-ttu-id="a1173-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1173-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1173-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1173-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1173-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1173-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1173-122">**.NET framework のバージョン:** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="a1173-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1173-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1173-123">See also</span></span>

- [<span data-ttu-id="a1173-124">ICorDebugRemote インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1173-124">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="a1173-125">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1173-125">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="a1173-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1173-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
