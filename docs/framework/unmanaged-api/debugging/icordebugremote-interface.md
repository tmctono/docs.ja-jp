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
ms.openlocfilehash: 0cc79c0a93fa4f05b8c793a8b7fb0b9b3f031b1a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791962"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="bcbf6-102">ICorDebugRemote インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcbf6-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="bcbf6-103">リモート ターゲット プロセスに対してマネージド デバッガーを起動または接続する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="bcbf6-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcbf6-104">構文</span><span class="sxs-lookup"><span data-stu-id="bcbf6-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="bcbf6-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="bcbf6-105">Methods</span></span>  
  
|<span data-ttu-id="bcbf6-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="bcbf6-106">Method</span></span>|<span data-ttu-id="bcbf6-107">説明</span><span class="sxs-lookup"><span data-stu-id="bcbf6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bcbf6-108">ICorDebugRemote::CreateProcessEx メソッド</span><span class="sxs-lookup"><span data-stu-id="bcbf6-108">ICorDebugRemote::CreateProcessEx Method</span></span>](icordebugremote-createprocessex-method.md)|<span data-ttu-id="bcbf6-109">マネージデバッグ用にリモートコンピューター上にプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="bcbf6-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="bcbf6-110">ICorDebugRemote::DebugActiveProcessEx メソッド</span><span class="sxs-lookup"><span data-stu-id="bcbf6-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="bcbf6-111">デバッガーでリモートコンピューター上のプロセスを起動します。</span><span class="sxs-lookup"><span data-stu-id="bcbf6-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcbf6-112">コメント</span><span class="sxs-lookup"><span data-stu-id="bcbf6-112">Remarks</span></span>  
 <span data-ttu-id="bcbf6-113">現在、この機能は、リモートの Macintosh コンピューターで実行されている Silverlight ベースのアプリケーションターゲットをデバッグする場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bcbf6-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcbf6-114">要件</span><span class="sxs-lookup"><span data-stu-id="bcbf6-114">Requirements</span></span>  
 <span data-ttu-id="bcbf6-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcbf6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcbf6-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bcbf6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bcbf6-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcbf6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcbf6-118">**.NET Framework のバージョン:** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="bcbf6-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcbf6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcbf6-119">See also</span></span>

- [<span data-ttu-id="bcbf6-120">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcbf6-120">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="bcbf6-121">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcbf6-121">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="bcbf6-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcbf6-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
