---
title: ICLRRuntimeInfo::LoadErrorString メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
ms.openlocfilehash: da6efae38cd70a68feea56b12e86be23fde7f0cb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762189"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="af34f-102">ICLRRuntimeInfo::LoadErrorString メソッド</span><span class="sxs-lookup"><span data-stu-id="af34f-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="af34f-103">HRESULT 値を、指定したカルチャの適切なエラーメッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="af34f-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="af34f-104">このメソッドは、次の関数を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="af34f-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="af34f-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="af34f-105">LoadStringRC</span></span>](loadstringrc-function.md)  
  
- [<span data-ttu-id="af34f-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="af34f-106">LoadStringRCEx</span></span>](loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="af34f-107">構文</span><span class="sxs-lookup"><span data-stu-id="af34f-107">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af34f-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af34f-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="af34f-109">から変換する HRESULT。</span><span class="sxs-lookup"><span data-stu-id="af34f-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="af34f-110">入出力指定した HRESULT に関連付けられているメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="af34f-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="af34f-111">[入力、出力]`pwzbuffer`バッファーオーバーランを回避するためののサイズ。</span><span class="sxs-lookup"><span data-stu-id="af34f-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="af34f-112">`pwzbuffer`が null の場合、は、 `pcchBuffer` の予期されるサイズを提供して、事前割り当て `pwzbuffer` を可能にします。</span><span class="sxs-lookup"><span data-stu-id="af34f-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="af34f-113">からカルチャ識別子。</span><span class="sxs-lookup"><span data-stu-id="af34f-113">[in] The culture identifier.</span></span> <span data-ttu-id="af34f-114">既定のカルチャを使用するには、-1 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af34f-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af34f-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="af34f-115">Return Value</span></span>  
 <span data-ttu-id="af34f-116">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="af34f-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="af34f-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af34f-117">HRESULT</span></span>|<span data-ttu-id="af34f-118">説明</span><span class="sxs-lookup"><span data-stu-id="af34f-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="af34f-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="af34f-119">S_OK</span></span>|<span data-ttu-id="af34f-120">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="af34f-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="af34f-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="af34f-121">E_POINTER</span></span>|<span data-ttu-id="af34f-122">`pcchBuffer` が null です。</span><span class="sxs-lookup"><span data-stu-id="af34f-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="af34f-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="af34f-123">E_INVALIDARG</span></span>|<span data-ttu-id="af34f-124">`pwzBuffer` が null です。</span><span class="sxs-lookup"><span data-stu-id="af34f-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af34f-125">要件</span><span class="sxs-lookup"><span data-stu-id="af34f-125">Requirements</span></span>  
 <span data-ttu-id="af34f-126">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af34f-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af34f-127">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="af34f-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="af34f-128">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="af34f-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af34f-129">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af34f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af34f-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="af34f-130">See also</span></span>

- [<span data-ttu-id="af34f-131">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af34f-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="af34f-132">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af34f-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="af34f-133">ホスティング</span><span class="sxs-lookup"><span data-stu-id="af34f-133">Hosting</span></span>](index.md)
