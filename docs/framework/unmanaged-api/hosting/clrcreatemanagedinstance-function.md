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
ms.openlocfilehash: 4e672030ae83b57da6f9ab66630513d79f28b8f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131997"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="e4e19-102">ClrCreateManagedInstance 関数</span><span class="sxs-lookup"><span data-stu-id="e4e19-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="e4e19-103">指定したマネージド型のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4e19-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="e4e19-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="e4e19-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="e4e19-105">COM アクティブ化を使用してマネージ型のインスタンスを作成するか、ホストを使用します (「 [.NET Framework 4 および4.5 で追加された CLR ホストインターフェイス](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e4e19-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4e19-106">構文</span><span class="sxs-lookup"><span data-stu-id="e4e19-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4e19-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e4e19-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="e4e19-108">から要求されているインスタンス型の名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e4e19-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="e4e19-109">から要求されているインスタンスの型の `IID`。</span><span class="sxs-lookup"><span data-stu-id="e4e19-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="e4e19-110">入出力呼び出し元によって要求されたマネージ型のインスタンスへのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e4e19-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4e19-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="e4e19-111">Remarks</span></span>  
 <span data-ttu-id="e4e19-112">共通言語ランタイムは、既にプロセスに読み込まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4e19-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="e4e19-113">たとえば、`ClrCreateManagedInstance` 関数が呼び出される前に、 [Corbindtoruntimeex](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)関数の呼び出しを使用して読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="e4e19-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="e4e19-114">ランタイムが読み込まれていない場合、`ClrCreateManagedInstance` は最初にランタイムの v v1.0.3705 の読み込みを試行します。</span><span class="sxs-lookup"><span data-stu-id="e4e19-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="e4e19-115">失敗した場合は、ランタイムの最新バージョンの読み込みが試行されます。</span><span class="sxs-lookup"><span data-stu-id="e4e19-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4e19-116">［要件］</span><span class="sxs-lookup"><span data-stu-id="e4e19-116">Requirements</span></span>  
 <span data-ttu-id="e4e19-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4e19-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4e19-118">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e4e19-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4e19-119">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e4e19-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4e19-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4e19-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e19-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4e19-121">See also</span></span>

- [<span data-ttu-id="e4e19-122">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="e4e19-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="e4e19-123">ホスティング</span><span class="sxs-lookup"><span data-stu-id="e4e19-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
