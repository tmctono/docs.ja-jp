---
title: ICorDebugRemote::CreateProcessEx メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a38812803127857281f9766fa3ed551971ec0330
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782786"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="1f642-102">ICorDebugRemote::CreateProcessEx メソッド</span><span class="sxs-lookup"><span data-stu-id="1f642-102">ICorDebugRemote::CreateProcessEx Method</span></span>
<span data-ttu-id="1f642-103">デバッガーでのリモート コンピューター上のプロセスを起動します。</span><span class="sxs-lookup"><span data-stu-id="1f642-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f642-104">構文</span><span class="sxs-lookup"><span data-stu-id="1f642-104">Syntax</span></span>  
  
```  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f642-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f642-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="1f642-106">[in]ポインター、 [ICorDebugRemoteTarget インターフェイス](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f642-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="1f642-107">プロセスの起動をリモート コンピューターを決定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="1f642-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="1f642-108">[in]実行中のプロセスによって実行されるモジュールを指定する null で終わる文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1f642-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="1f642-109">モジュールは、呼び出し元のプロセスのセキュリティ コンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="1f642-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="1f642-110">[in]実行中のプロセスによって実行されるコマンドラインを指定する null で終わる文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1f642-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="1f642-111">[in]リモート デバッグに使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1f642-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="1f642-112">[in]リモート デバッグに使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1f642-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="1f642-113">[in]リモート デバッグに使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1f642-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="1f642-114">[in]リモート デバッグに使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1f642-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="1f642-115">[in]新しいプロセスの環境ブロックへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1f642-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="1f642-116">[in]プロセスの現在のディレクトリにフルパスを指定する null で終わる文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1f642-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="1f642-117">このパラメーターが null の場合、新しいプロセスは、呼び出し元プロセスとして同じの現在のドライブとディレクトリがあります。</span><span class="sxs-lookup"><span data-stu-id="1f642-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="1f642-118">[in]リモート デバッグに使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1f642-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="1f642-119">[in]リモート デバッグに使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1f642-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="1f642-120">[in]リモート デバッグに使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1f642-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="1f642-121">[out]プロセスを表す「ICorDebugProcess インターフェイス」オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1f642-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f642-122">戻り値</span><span class="sxs-lookup"><span data-stu-id="1f642-122">Return Value</span></span>  
 <span data-ttu-id="1f642-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f642-123">S_OK</span></span>  
 <span data-ttu-id="1f642-124">デバッグ、リモート コンピューターに返される「ICorDebugProcess インターフェイス」プロセスが正常に起動します。</span><span class="sxs-lookup"><span data-stu-id="1f642-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="1f642-125">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="1f642-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="1f642-126">リモート コンピューター上のプロセスを起動してデバッグ「ICorDebugProcess インターフェイス」を返すことができません。</span><span class="sxs-lookup"><span data-stu-id="1f642-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f642-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f642-127">Remarks</span></span>  
 <span data-ttu-id="1f642-128">Silverlight では、混合モード デバッグはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1f642-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f642-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="1f642-129">Requirements</span></span>  
 <span data-ttu-id="1f642-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f642-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f642-131">**ヘッダー:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="1f642-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="1f642-132">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f642-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f642-133">**.NET framework のバージョン:** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="1f642-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f642-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f642-134">See also</span></span>

- [<span data-ttu-id="1f642-135">ICorDebugRemote インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f642-135">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="1f642-136">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f642-136">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="1f642-137">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f642-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
