---
title: ICLRRuntimeInfo::SetDefaultStartupFlags メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
ms.openlocfilehash: aa02d42511a863434fef236f90afae2c5417a78d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504018"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="504d8-102">ICLRRuntimeInfo::SetDefaultStartupFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="504d8-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="504d8-103">ランタイムを開始するために使用されるスタートアップフラグとホスト構成ファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="504d8-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="504d8-104">このメソッドは、 `startupFlags` [Corbindtoruntimeex](corbindtoruntimeex-function.md)および[Corbindtoruntimeex](corbindtoruntimehost-function.md)関数でのパラメーターの使用よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="504d8-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="504d8-105">構文</span><span class="sxs-lookup"><span data-stu-id="504d8-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="504d8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="504d8-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="504d8-107">から設定するホストスタートアップフラグ。</span><span class="sxs-lookup"><span data-stu-id="504d8-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="504d8-108">[Corbindtoruntimeex](corbindtoruntimeex-function.md)および[Corbindtoruntimeex](corbindtoruntimehost-function.md)関数と同じフラグを使用します。</span><span class="sxs-lookup"><span data-stu-id="504d8-108">Use the same flags as with the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="504d8-109">から設定するホスト構成ファイルのディレクトリパス。</span><span class="sxs-lookup"><span data-stu-id="504d8-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="504d8-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="504d8-110">Return Value</span></span>  
 <span data-ttu-id="504d8-111">このメソッドは、次の特定の HRESULT と、メソッドエラーを示す HRESULT エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="504d8-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="504d8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="504d8-112">HRESULT</span></span>|<span data-ttu-id="504d8-113">説明</span><span class="sxs-lookup"><span data-stu-id="504d8-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="504d8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="504d8-114">S_OK</span></span>|<span data-ttu-id="504d8-115">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="504d8-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="504d8-116">解説</span><span class="sxs-lookup"><span data-stu-id="504d8-116">Remarks</span></span>  
 <span data-ttu-id="504d8-117">マルチスレッドホストは、このメソッドの呼び出しを同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="504d8-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="504d8-118">それ以外の場合、スレッド B は、の `SetStartupFlags` 呼び出しを完了し `SetStartupFlags` てからランタイムを開始する前に、メソッドを呼び出すことがあります。</span><span class="sxs-lookup"><span data-stu-id="504d8-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="504d8-119">要件</span><span class="sxs-lookup"><span data-stu-id="504d8-119">Requirements</span></span>  
 <span data-ttu-id="504d8-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="504d8-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="504d8-121">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="504d8-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="504d8-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="504d8-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="504d8-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="504d8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="504d8-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="504d8-124">See also</span></span>

- [<span data-ttu-id="504d8-125">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="504d8-125">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="504d8-126">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="504d8-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="504d8-127">ホスティング</span><span class="sxs-lookup"><span data-stu-id="504d8-127">Hosting</span></span>](index.md)
