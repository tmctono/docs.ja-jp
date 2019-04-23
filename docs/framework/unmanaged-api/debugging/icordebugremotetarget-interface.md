---
title: ICorDebugRemoteTarget インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae31506d4ba34bf262f49bc2321c6cfcd30f1b60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197322"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="23d04-102">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23d04-102">ICorDebugRemoteTarget Interface</span></span>
<span data-ttu-id="23d04-103">開発者が共通言語ランタイム (CLR: Common Language Runtime) 環境で Silverlight ベース アプリケーションをデバッグできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="23d04-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d04-104">構文</span><span class="sxs-lookup"><span data-stu-id="23d04-104">Syntax</span></span>  
  
```  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="23d04-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="23d04-105">Methods</span></span>  
  
|<span data-ttu-id="23d04-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="23d04-106">Method</span></span>|<span data-ttu-id="23d04-107">説明</span><span class="sxs-lookup"><span data-stu-id="23d04-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23d04-108">ICorDebugRemoteTarget::GetHostName メソッド</span><span class="sxs-lookup"><span data-stu-id="23d04-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="23d04-109">リモート マシンのホスト名または IP アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="23d04-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23d04-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="23d04-110">Remarks</span></span>  
 <span data-ttu-id="23d04-111">Windows 95、Windows 98、Windows ME、または x86 以外のプラットフォーム (IA-64、AMD64 など) では、混合モード (つまり、マネージド コードとネイティブ コード) デバッグはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="23d04-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23d04-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="23d04-112">Requirements</span></span>  
 <span data-ttu-id="23d04-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="23d04-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23d04-114">**ヘッダー:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="23d04-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="23d04-115">**ライブラリ:** :CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23d04-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="23d04-116">**.NET framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="23d04-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d04-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="23d04-117">See also</span></span>

- [<span data-ttu-id="23d04-118">ICorDebugRemote インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23d04-118">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="23d04-119">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23d04-119">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="23d04-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23d04-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
