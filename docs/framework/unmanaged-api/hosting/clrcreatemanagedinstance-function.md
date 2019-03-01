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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5103490da7f3056cf95f7986b46837e059f8212f
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211833"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="944e9-102">ClrCreateManagedInstance 関数</span><span class="sxs-lookup"><span data-stu-id="944e9-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="944e9-103">指定したマネージド型のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="944e9-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="944e9-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="944e9-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="944e9-105">COM アクティブ化を使用して、管理対象の型のインスタンスを作成するか、ホストを使用して、(を参照してください[CLR をホストしている .NET Framework 4 および 4.5 で追加されたインターフェイス](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md))。</span><span class="sxs-lookup"><span data-stu-id="944e9-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="944e9-106">構文</span><span class="sxs-lookup"><span data-stu-id="944e9-106">Syntax</span></span>  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="944e9-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="944e9-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="944e9-108">[in]要求されているインスタンス型の名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="944e9-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="944e9-109">[in]`IID`の要求されているインスタンスの型。</span><span class="sxs-lookup"><span data-stu-id="944e9-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="944e9-110">[out]呼び出し元によって要求されたマネージ型のインスタンスへのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="944e9-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="944e9-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="944e9-111">Remarks</span></span>  
 <span data-ttu-id="944e9-112">共通言語ランタイムは、プロセスに既に読み込まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="944e9-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="944e9-113">などへの呼び出しを使用して読み込むことがあります、 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)関数の前に、`ClrCreateManagedInstance`関数が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="944e9-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="944e9-114">ランタイムが読み込まれていない場合`ClrCreateManagedInstance`最初 v1.0.3705、ランタイムの読み込みを試みます。</span><span class="sxs-lookup"><span data-stu-id="944e9-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="944e9-115">失敗した場合、ランタイムの最新バージョンをロードしようとします。</span><span class="sxs-lookup"><span data-stu-id="944e9-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="944e9-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="944e9-116">Requirements</span></span>  
 <span data-ttu-id="944e9-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="944e9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="944e9-118">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="944e9-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="944e9-119">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="944e9-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="944e9-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="944e9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="944e9-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="944e9-121">See also</span></span>
- [<span data-ttu-id="944e9-122">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="944e9-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="944e9-123">ホスティング</span><span class="sxs-lookup"><span data-stu-id="944e9-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
