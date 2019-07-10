---
title: ICorDebugRemote インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugRemote
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemote
helpviewer_keywords:
- ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbed34f53ff43ca7887a58b3c879eaa74703da3e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744750"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="eb75a-102">ICorDebugRemote インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb75a-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="eb75a-103">リモート ターゲット プロセスに対してマネージド デバッガーを起動または接続する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="eb75a-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb75a-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb75a-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugRemote : IUnknown  
{  
    HRESULT CreateProcessEx  
      (  
      [in] ICorDebugRemoteTarget *     pRemoteTarget,  
      [in] LPCWSTR                     lpApplicationName,  
      [in] LPWSTR                      lpCommandLine,  
      [in] LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
      [in] LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
      [in] BOOL                        bInheritHandles,  
      [in] DWORD                       dwCreationFlags,  
      [in] PVOID                       lpEnvironment,  
      [in] LPCWSTR                     lpCurrentDirectory,  
      [in] LPSTARTUPINFOW              lpStartupInfo,  
      [in] LPPROCESS_INFORMATION       lpProcessInformation,  
      [in] CorDebugCreateProcessFlags  debuggingFlags,  
      [out] ICorDebugProcess **        ppProcess  
      );  
  
    HRESULT DebugActiveProcessEx  
      (  
      [in] ICorDebugRemoteTarget *   pRemoteTarget,  
      [in] DWORD                     dwProcessId,  
      [in] BOOL                      fWin32Attach,  
      [out] ICorDebugProcess **      ppProcess  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="eb75a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="eb75a-105">Methods</span></span>  
  
|<span data-ttu-id="eb75a-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="eb75a-106">Method</span></span>|<span data-ttu-id="eb75a-107">説明</span><span class="sxs-lookup"><span data-stu-id="eb75a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb75a-108">ICorDebugRemote::CreateProcessEx メソッド</span><span class="sxs-lookup"><span data-stu-id="eb75a-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="eb75a-109">マネージ デバッグのために、リモート コンピューターでプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb75a-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="eb75a-110">ICorDebugRemote::DebugActiveProcessEx メソッド</span><span class="sxs-lookup"><span data-stu-id="eb75a-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="eb75a-111">デバッガーでのリモート コンピューター上のプロセスを起動します。</span><span class="sxs-lookup"><span data-stu-id="eb75a-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb75a-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="eb75a-112">Remarks</span></span>  
 <span data-ttu-id="eb75a-113">現時点では、Macintosh コンピューターをリモートで実行されている Silverlight ベースのアプリケーションのターゲットのデバッグにのみ、この機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eb75a-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb75a-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="eb75a-114">Requirements</span></span>  
 <span data-ttu-id="eb75a-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb75a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb75a-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb75a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb75a-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb75a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb75a-118">**.NET framework のバージョン:** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="eb75a-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb75a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb75a-119">See also</span></span>

- [<span data-ttu-id="eb75a-120">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb75a-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="eb75a-121">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb75a-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="eb75a-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb75a-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
