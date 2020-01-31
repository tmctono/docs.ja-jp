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
ms.openlocfilehash: b78bff2994cefc6c35a4bd59133338392c3a1b24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791976"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="8e746-102">ICorDebugRemote::DebugActiveProcessEx メソッド</span><span class="sxs-lookup"><span data-stu-id="8e746-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="8e746-103">デバッガーでリモートコンピューター上のプロセスを起動します。</span><span class="sxs-lookup"><span data-stu-id="8e746-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e746-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e746-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e746-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8e746-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="8e746-106">からツールの[ターゲットインターフェイス](icordebugremotetarget-interface.md)を指すポインター。</span><span class="sxs-lookup"><span data-stu-id="8e746-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="8e746-107">このパラメーターは、プロセスが実行されているコンピューターを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8e746-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="8e746-108">からデバッガーがアタッチされるプロセスの ID。</span><span class="sxs-lookup"><span data-stu-id="8e746-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="8e746-109">[in] デバッガーをプロセスの Win32 デバッガーとして動作させる必要があるかどうかを `true` し、アンマネージコールバックをディスパッチします。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="8e746-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="8e746-110">入出力デバッガーがアタッチされているプロセスを表す "いいプロセス" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8e746-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e746-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="8e746-111">Return Value</span></span>  
 <span data-ttu-id="8e746-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e746-112">S_OK</span></span>  
 <span data-ttu-id="8e746-113">リモートコンピューター上のプロセスに正常にアタッチされました。</span><span class="sxs-lookup"><span data-stu-id="8e746-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="8e746-114">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="8e746-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="8e746-115">リモートコンピューター上のプロセスにアタッチできません。</span><span class="sxs-lookup"><span data-stu-id="8e746-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e746-116">コメント</span><span class="sxs-lookup"><span data-stu-id="8e746-116">Remarks</span></span>  
 <span data-ttu-id="8e746-117">混合モードのデバッグは、Silverlight ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8e746-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e746-118">要件</span><span class="sxs-lookup"><span data-stu-id="8e746-118">Requirements</span></span>  
 <span data-ttu-id="8e746-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e746-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e746-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e746-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e746-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e746-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e746-122">**.NET Framework のバージョン:** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="8e746-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e746-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e746-123">See also</span></span>

- [<span data-ttu-id="8e746-124">ICorDebugRemote インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e746-124">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="8e746-125">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e746-125">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="8e746-126">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e746-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
