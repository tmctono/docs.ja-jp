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
ms.openlocfilehash: ef11aa48f679592126f736c2877c697f02cb5e62
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379239"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="5fc75-102">ICorDebugRemote インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5fc75-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="5fc75-103">リモート ターゲット プロセスに対してマネージド デバッガーを起動または接続する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="5fc75-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fc75-104">構文</span><span class="sxs-lookup"><span data-stu-id="5fc75-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="5fc75-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5fc75-105">Methods</span></span>  
  
|<span data-ttu-id="5fc75-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="5fc75-106">Method</span></span>|<span data-ttu-id="5fc75-107">説明</span><span class="sxs-lookup"><span data-stu-id="5fc75-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5fc75-108">ICorDebugRemote::CreateProcessEx メソッド</span><span class="sxs-lookup"><span data-stu-id="5fc75-108">ICorDebugRemote::CreateProcessEx Method</span></span>](icordebugremote-createprocessex-method.md)|<span data-ttu-id="5fc75-109">マネージデバッグ用にリモートコンピューター上にプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5fc75-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="5fc75-110">ICorDebugRemote::DebugActiveProcessEx メソッド</span><span class="sxs-lookup"><span data-stu-id="5fc75-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="5fc75-111">デバッガーでリモートコンピューター上のプロセスを起動します。</span><span class="sxs-lookup"><span data-stu-id="5fc75-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fc75-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="5fc75-112">Remarks</span></span>  
 <span data-ttu-id="5fc75-113">現在、この機能は、リモートの Macintosh コンピューターで実行されている Silverlight ベースのアプリケーションターゲットをデバッグする場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5fc75-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fc75-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="5fc75-114">Requirements</span></span>  
 <span data-ttu-id="5fc75-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fc75-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fc75-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fc75-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fc75-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fc75-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fc75-118">**.NET Framework のバージョン:** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="5fc75-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fc75-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fc75-119">See also</span></span>

- [<span data-ttu-id="5fc75-120">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5fc75-120">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="5fc75-121">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5fc75-121">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="5fc75-122">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="5fc75-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
