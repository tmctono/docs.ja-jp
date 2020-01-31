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
ms.openlocfilehash: cfec84483d387630623f77c176c668171303dd0f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791989"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="bae26-102">ICorDebugRemote::CreateProcessEx メソッド</span><span class="sxs-lookup"><span data-stu-id="bae26-102">ICorDebugRemote::CreateProcessEx Method</span></span>
<span data-ttu-id="bae26-103">デバッガーでリモートコンピューター上のプロセスを起動します。</span><span class="sxs-lookup"><span data-stu-id="bae26-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bae26-104">構文</span><span class="sxs-lookup"><span data-stu-id="bae26-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="bae26-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bae26-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="bae26-106">からツールの[ターゲットインターフェイス](icordebugremotetarget-interface.md)を指すポインター。</span><span class="sxs-lookup"><span data-stu-id="bae26-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="bae26-107">プロセスを起動するリモートコンピューターを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bae26-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="bae26-108">から起動されたプロセスによって実行されるモジュールを指定する、null で終わる文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bae26-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="bae26-109">モジュールは、呼び出し元プロセスのセキュリティコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="bae26-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="bae26-110">から起動されたプロセスによって実行されるコマンドラインを指定する、null で終わる文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bae26-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="bae26-111">からリモートデバッグには使用されません。</span><span class="sxs-lookup"><span data-stu-id="bae26-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="bae26-112">からリモートデバッグには使用されません。</span><span class="sxs-lookup"><span data-stu-id="bae26-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="bae26-113">からリモートデバッグには使用されません。</span><span class="sxs-lookup"><span data-stu-id="bae26-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="bae26-114">からリモートデバッグには使用されません。</span><span class="sxs-lookup"><span data-stu-id="bae26-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="bae26-115">から新しいプロセスの環境ブロックへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bae26-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="bae26-116">からプロセスの現在のディレクトリへの完全パスを指定する、null で終わる文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bae26-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="bae26-117">このパラメーターが null の場合、新しいプロセスは呼び出しプロセスと同じ現在のドライブとディレクトリを持ちます。</span><span class="sxs-lookup"><span data-stu-id="bae26-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="bae26-118">からリモートデバッグには使用されません。</span><span class="sxs-lookup"><span data-stu-id="bae26-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="bae26-119">からリモートデバッグには使用されません。</span><span class="sxs-lookup"><span data-stu-id="bae26-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="bae26-120">からリモートデバッグには使用されません。</span><span class="sxs-lookup"><span data-stu-id="bae26-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="bae26-121">入出力プロセスを表す "いいプロセスインターフェイス" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bae26-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bae26-122">戻り値</span><span class="sxs-lookup"><span data-stu-id="bae26-122">Return Value</span></span>  
 <span data-ttu-id="bae26-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="bae26-123">S_OK</span></span>  
 <span data-ttu-id="bae26-124">リモートコンピューターでプロセスが正常に起動され、デバッグのために "のプロセスインターフェイス" が返されました。</span><span class="sxs-lookup"><span data-stu-id="bae26-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="bae26-125">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="bae26-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="bae26-126">リモートコンピューターでプロセスを起動できず、デバッグのために "のプロセスインターフェイス" を返します。</span><span class="sxs-lookup"><span data-stu-id="bae26-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bae26-127">コメント</span><span class="sxs-lookup"><span data-stu-id="bae26-127">Remarks</span></span>  
 <span data-ttu-id="bae26-128">混合モードのデバッグは、Silverlight ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bae26-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bae26-129">要件</span><span class="sxs-lookup"><span data-stu-id="bae26-129">Requirements</span></span>  
 <span data-ttu-id="bae26-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bae26-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bae26-131">**ヘッダー:** CorDebug .idl</span><span class="sxs-lookup"><span data-stu-id="bae26-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="bae26-132">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bae26-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bae26-133">**.NET Framework のバージョン:** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="bae26-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bae26-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="bae26-134">See also</span></span>

- [<span data-ttu-id="bae26-135">ICorDebugRemote インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bae26-135">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="bae26-136">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bae26-136">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="bae26-137">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bae26-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
