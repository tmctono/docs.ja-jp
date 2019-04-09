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
ms.openlocfilehash: a50a799c625c647aa275994bc92738b8a4267eec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135578"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="215da-102">ICorDebugRemote インターフェイス</span><span class="sxs-lookup"><span data-stu-id="215da-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="215da-103">リモート ターゲット プロセスに対してマネージド デバッガーを起動または接続する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="215da-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="215da-104">構文</span><span class="sxs-lookup"><span data-stu-id="215da-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="215da-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="215da-105">Methods</span></span>  
  
|<span data-ttu-id="215da-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="215da-106">Method</span></span>|<span data-ttu-id="215da-107">説明</span><span class="sxs-lookup"><span data-stu-id="215da-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="215da-108">ICorDebugRemote::CreateProcessEx メソッド</span><span class="sxs-lookup"><span data-stu-id="215da-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="215da-109">マネージ デバッグのために、リモート コンピューターでプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="215da-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="215da-110">ICorDebugRemote::DebugActiveProcessEx メソッド</span><span class="sxs-lookup"><span data-stu-id="215da-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="215da-111">デバッガーでのリモート コンピューター上のプロセスを起動します。</span><span class="sxs-lookup"><span data-stu-id="215da-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="215da-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="215da-112">Remarks</span></span>  
 <span data-ttu-id="215da-113">現時点では、Macintosh コンピューターをリモートで実行されている Silverlight ベースのアプリケーションのターゲットのデバッグにのみ、この機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="215da-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="215da-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="215da-114">Requirements</span></span>  
 <span data-ttu-id="215da-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="215da-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="215da-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="215da-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="215da-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="215da-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="215da-118">**.NET framework のバージョン:** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="215da-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="215da-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="215da-119">See also</span></span>

- [<span data-ttu-id="215da-120">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="215da-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="215da-121">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="215da-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="215da-122">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="215da-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
