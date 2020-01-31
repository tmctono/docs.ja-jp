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
ms.openlocfilehash: ecd4ad31b8dad55e9538642a4dc652341bc84b97
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784671"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="d5340-102">ICorDebugAssembly インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5340-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="d5340-103">アセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="d5340-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5340-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d5340-104">Methods</span></span>  
  
|<span data-ttu-id="d5340-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d5340-105">Method</span></span>|<span data-ttu-id="d5340-106">説明</span><span class="sxs-lookup"><span data-stu-id="d5340-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5340-107">EnumerateModules メソッド</span><span class="sxs-lookup"><span data-stu-id="d5340-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="d5340-108">アセンブリに格納されているモジュールの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="d5340-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="d5340-109">GetAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="d5340-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="d5340-110">この `ICorDebugAssembly` インスタンスを含むアプリケーションドメインへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="d5340-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="d5340-111">GetCodeBase メソッド</span><span class="sxs-lookup"><span data-stu-id="d5340-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="d5340-112">.NET Framework の現在のバージョンでは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="d5340-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="d5340-113">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="d5340-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="d5340-114">アセンブリの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="d5340-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="d5340-115">GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="d5340-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="d5340-116">アセンブリが実行されている、のプロセスインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d5340-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5340-117">コメント</span><span class="sxs-lookup"><span data-stu-id="d5340-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d5340-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d5340-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5340-119">要件</span><span class="sxs-lookup"><span data-stu-id="d5340-119">Requirements</span></span>  
 <span data-ttu-id="d5340-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5340-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5340-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5340-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5340-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5340-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5340-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5340-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5340-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5340-124">See also</span></span>

- [<span data-ttu-id="d5340-125">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5340-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
