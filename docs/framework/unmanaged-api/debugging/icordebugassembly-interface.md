---
title: ICorDebugAssembly インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
ms.openlocfilehash: dea3231e3bbb361b56254756c6d99b115f73e792
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133967"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="0a4d4-102">ICorDebugAssembly インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0a4d4-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="0a4d4-103">アセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="0a4d4-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0a4d4-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="0a4d4-104">Methods</span></span>  
  
|<span data-ttu-id="0a4d4-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0a4d4-105">Method</span></span>|<span data-ttu-id="0a4d4-106">説明</span><span class="sxs-lookup"><span data-stu-id="0a4d4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0a4d4-107">EnumerateModules メソッド</span><span class="sxs-lookup"><span data-stu-id="0a4d4-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="0a4d4-108">アセンブリに格納されているモジュールの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="0a4d4-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="0a4d4-109">GetAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="0a4d4-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="0a4d4-110">この `ICorDebugAssembly` インスタンスを含むアプリケーションドメインへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="0a4d4-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="0a4d4-111">GetCodeBase メソッド</span><span class="sxs-lookup"><span data-stu-id="0a4d4-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="0a4d4-112">.NET Framework の現在のバージョンでは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="0a4d4-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="0a4d4-113">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="0a4d4-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="0a4d4-114">アセンブリの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="0a4d4-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="0a4d4-115">GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="0a4d4-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="0a4d4-116">アセンブリが実行されている、のプロセスインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="0a4d4-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a4d4-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="0a4d4-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a4d4-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0a4d4-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a4d4-119">［要件］</span><span class="sxs-lookup"><span data-stu-id="0a4d4-119">Requirements</span></span>  
 <span data-ttu-id="0a4d4-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a4d4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a4d4-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a4d4-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a4d4-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a4d4-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a4d4-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a4d4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4d4-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a4d4-124">See also</span></span>

- [<span data-ttu-id="0a4d4-125">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0a4d4-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
