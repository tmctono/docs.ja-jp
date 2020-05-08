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
ms.openlocfilehash: d9e2236b944137de82bb056820f81014febfcc5f
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894894"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="c7113-102">ICorDebugAssembly インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c7113-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="c7113-103">アセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="c7113-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7113-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="c7113-104">Methods</span></span>  
  
|<span data-ttu-id="c7113-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c7113-105">Method</span></span>|<span data-ttu-id="c7113-106">説明</span><span class="sxs-lookup"><span data-stu-id="c7113-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7113-107">EnumerateModules メソッド</span><span class="sxs-lookup"><span data-stu-id="c7113-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="c7113-108">アセンブリに格納されているモジュールの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="c7113-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="c7113-109">GetAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="c7113-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="c7113-110">この`ICorDebugAssembly`インスタンスを含むアプリケーションドメインへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="c7113-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="c7113-111">GetCodeBase メソッド</span><span class="sxs-lookup"><span data-stu-id="c7113-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="c7113-112">.NET Framework の現在のバージョンでは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="c7113-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="c7113-113">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="c7113-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="c7113-114">アセンブリの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="c7113-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="c7113-115">GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="c7113-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="c7113-116">アセンブリが実行されている、のプロセスインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c7113-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7113-117">解説</span><span class="sxs-lookup"><span data-stu-id="c7113-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7113-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c7113-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7113-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="c7113-119">Requirements</span></span>  
 <span data-ttu-id="c7113-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7113-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7113-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7113-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7113-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7113-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7113-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7113-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7113-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7113-124">See also</span></span>

- [<span data-ttu-id="c7113-125">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c7113-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
