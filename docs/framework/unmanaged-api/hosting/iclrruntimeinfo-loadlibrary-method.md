---
title: ICLRRuntimeInfo::LoadLibrary メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65ac05a524297029ca50970bdd231c6a9112e35c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748385"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="f6b95-102">ICLRRuntimeInfo::LoadLibrary メソッド</span><span class="sxs-lookup"><span data-stu-id="f6b95-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="f6b95-103">によって表される共通言語ランタイム (CLR) から .NET Framework ライブラリを読み込み、 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="f6b95-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="f6b95-104">このメソッドは、 [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="f6b95-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6b95-105">構文</span><span class="sxs-lookup"><span data-stu-id="f6b95-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6b95-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6b95-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="f6b95-107">[in]読み込まれるアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="f6b95-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="f6b95-108">[out]読み込まれたアセンブリへのハンドル。</span><span class="sxs-lookup"><span data-stu-id="f6b95-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6b95-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="f6b95-109">Return Value</span></span>  
 <span data-ttu-id="f6b95-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="f6b95-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f6b95-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6b95-111">HRESULT</span></span>|<span data-ttu-id="f6b95-112">説明</span><span class="sxs-lookup"><span data-stu-id="f6b95-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6b95-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6b95-113">S_OK</span></span>|<span data-ttu-id="f6b95-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="f6b95-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="f6b95-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f6b95-115">E_POINTER</span></span>|<span data-ttu-id="f6b95-116">`pwzDllName` または `phndModule` が null です。</span><span class="sxs-lookup"><span data-stu-id="f6b95-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="f6b95-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f6b95-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f6b95-118">メモリが不足は、要求を処理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6b95-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6b95-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="f6b95-119">Remarks</span></span>  
 <span data-ttu-id="f6b95-120">このメソッドは、.NET Framework 再頒布可能パッケージに含まれている Dll のみを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="f6b95-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="f6b95-121">ユーザーが生成したアセンブリを読み込むことことはできません。</span><span class="sxs-lookup"><span data-stu-id="f6b95-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6b95-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="f6b95-122">Requirements</span></span>  
 <span data-ttu-id="f6b95-123">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6b95-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6b95-124">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f6b95-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f6b95-125">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="f6b95-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6b95-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6b95-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b95-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6b95-127">See also</span></span>

- [<span data-ttu-id="f6b95-128">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f6b95-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="f6b95-129">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f6b95-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="f6b95-130">ホスティング</span><span class="sxs-lookup"><span data-stu-id="f6b95-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
