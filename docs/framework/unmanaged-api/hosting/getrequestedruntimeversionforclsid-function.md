---
title: GetRequestedRuntimeVersionForCLSID 関数
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7a6b73006b6842032ae90c2c7a8433f5b58d175
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665055"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="f0488-102">GetRequestedRuntimeVersionForCLSID 関数</span><span class="sxs-lookup"><span data-stu-id="f0488-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="f0488-103">適切な共通言語ランタイム (CLR) のバージョン情報と、指定したクラスを取得します。`CLSID`します。</span><span class="sxs-lookup"><span data-stu-id="f0488-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="f0488-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="f0488-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0488-105">構文</span><span class="sxs-lookup"><span data-stu-id="f0488-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0488-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f0488-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="f0488-107">[in] `CLSID`のコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="f0488-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="f0488-108">[out] 正常完了時にバージョン番号の文字列を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="f0488-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f0488-109">[in] ワイド文字単位のサイズの`pVersion`バッファー。</span><span class="sxs-lookup"><span data-stu-id="f0488-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="f0488-110">[out]返されたバッファーの長さ、(バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="f0488-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="f0488-111">[in] CLSID_RESOLUTION_FLAGS 値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="f0488-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="f0488-112">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f0488-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="f0488-113">CLSID_RESOLUTION_DEFAULT:(0x0) 既定の相互運用機能の動作を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0488-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="f0488-114">CLSID_RESOLUTION_REGISTERED:(0x1)、レジストリを検索する必要があるし、shim のポリシーを適用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0488-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0488-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="f0488-115">Return Value</span></span>  
  
|<span data-ttu-id="f0488-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f0488-116">HRESULT</span></span>|<span data-ttu-id="f0488-117">説明</span><span class="sxs-lookup"><span data-stu-id="f0488-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0488-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0488-118">S_OK</span></span>|<span data-ttu-id="f0488-119">関数が正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="f0488-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="f0488-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f0488-120">E_INVALIDARG</span></span>|<span data-ttu-id="f0488-121">パラメーターの 1 つに、無効な型または形式。</span><span class="sxs-lookup"><span data-stu-id="f0488-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="f0488-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f0488-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f0488-123">`pVersion`バッファーはバージョン文字列全体を保持するために十分な大きさがありません。</span><span class="sxs-lookup"><span data-stu-id="f0488-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="f0488-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="f0488-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="f0488-125">クラスの指定した登録がない`CLSID`します。</span><span class="sxs-lookup"><span data-stu-id="f0488-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="f0488-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f0488-126">E_POINTER</span></span>|<span data-ttu-id="f0488-127">`dwLength` null の場合または`cchBuffer`バージョン文字列を保持するために十分な大きさが`pVersion`が null です。</span><span class="sxs-lookup"><span data-stu-id="f0488-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0488-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="f0488-128">Requirements</span></span>  
 <span data-ttu-id="f0488-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0488-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0488-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f0488-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0488-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0488-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0488-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0488-132">See also</span></span>

- [<span data-ttu-id="f0488-133">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="f0488-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
