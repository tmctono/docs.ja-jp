---
title: ClrCreateManagedInstance 関数
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: 7fbe0cf3e93d75749fa3f463f3f97dbd1bfe27a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176540"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="90e73-102">ClrCreateManagedInstance 関数</span><span class="sxs-lookup"><span data-stu-id="90e73-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="90e73-103">指定したマネージド型のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="90e73-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="90e73-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="90e73-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="90e73-105">COM アクティベーションを使用してマネージ型のインスタンスを作成するか、ホストを使用します[(.NET Framework 4 および 4.5 で追加された CLR ホスティング インターフェイス](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)を参照)。</span><span class="sxs-lookup"><span data-stu-id="90e73-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90e73-106">構文</span><span class="sxs-lookup"><span data-stu-id="90e73-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90e73-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="90e73-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="90e73-108">[in]要求されているインスタンス型の名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="90e73-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="90e73-109">[in]要求`IID`されているインスタンス型の。</span><span class="sxs-lookup"><span data-stu-id="90e73-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="90e73-110">[アウト]呼び出し元によって要求されたマネージ型のインスタンスへのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="90e73-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90e73-111">解説</span><span class="sxs-lookup"><span data-stu-id="90e73-111">Remarks</span></span>  
 <span data-ttu-id="90e73-112">共通言語ランタイムは、既にプロセスに読み込まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="90e73-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="90e73-113">たとえば、関数が呼び出される前`ClrCreateManagedInstance`に[、関数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)の呼び出しを使用して読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="90e73-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="90e73-114">ランタイムがロードされていない場合は、`ClrCreateManagedInstance`まずランタイムの v1.0.3705 のロードを試みます。</span><span class="sxs-lookup"><span data-stu-id="90e73-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="90e73-115">失敗した場合は、最新バージョンのランタイムを読み込もうとします。</span><span class="sxs-lookup"><span data-stu-id="90e73-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90e73-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="90e73-116">Requirements</span></span>  
 <span data-ttu-id="90e73-117">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90e73-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90e73-118">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="90e73-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90e73-119">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="90e73-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90e73-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90e73-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e73-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="90e73-121">See also</span></span>

- [<span data-ttu-id="90e73-122">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="90e73-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="90e73-123">ホスティング</span><span class="sxs-lookup"><span data-stu-id="90e73-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
