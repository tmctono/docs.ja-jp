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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2b802845e36e818a962484c1fea09cbcc1ceefd
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974576"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="d9cf8-102">ICorDebugAssembly インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9cf8-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="d9cf8-103">アセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="d9cf8-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9cf8-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d9cf8-104">Methods</span></span>  
  
|<span data-ttu-id="d9cf8-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d9cf8-105">Method</span></span>|<span data-ttu-id="d9cf8-106">説明</span><span class="sxs-lookup"><span data-stu-id="d9cf8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9cf8-107">EnumerateModules メソッド</span><span class="sxs-lookup"><span data-stu-id="d9cf8-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="d9cf8-108">アセンブリに含まれるモジュールの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="d9cf8-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="d9cf8-109">GetAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="d9cf8-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="d9cf8-110">これを含むアプリケーション ドメインへのインターフェイス ポインターを取得`ICorDebugAssembly`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d9cf8-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="d9cf8-111">GetCodeBase メソッド</span><span class="sxs-lookup"><span data-stu-id="d9cf8-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="d9cf8-112">.NET Framework の現在のバージョンでは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="d9cf8-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="d9cf8-113">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="d9cf8-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="d9cf8-114">アセンブリの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="d9cf8-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="d9cf8-115">GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="d9cf8-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="d9cf8-116">アセンブリが実行されている ICorDebugProcess インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d9cf8-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9cf8-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="d9cf8-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9cf8-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d9cf8-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9cf8-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="d9cf8-119">Requirements</span></span>  
 <span data-ttu-id="d9cf8-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9cf8-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9cf8-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9cf8-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9cf8-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9cf8-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9cf8-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9cf8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9cf8-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9cf8-124">See also</span></span>
- [<span data-ttu-id="d9cf8-125">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9cf8-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
