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
ms.openlocfilehash: 6132e94544b30486b70ecfec49c1ddd5e3c0f50b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178116"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="be85e-102">GetRequestedRuntimeVersionForCLSID 関数</span><span class="sxs-lookup"><span data-stu-id="be85e-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="be85e-103">指定した クラスの共通言語ランタイム (CLR) のバージョン情報を取得`CLSID`します。</span><span class="sxs-lookup"><span data-stu-id="be85e-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="be85e-104">この関数は、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="be85e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be85e-105">構文</span><span class="sxs-lookup"><span data-stu-id="be85e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be85e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="be85e-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="be85e-107">[in] コンポーネント`CLSID`の</span><span class="sxs-lookup"><span data-stu-id="be85e-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="be85e-108">[アウト] 正常終了した場合に、バージョン番号文字列を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="be85e-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="be85e-109">[in] `pVersion`バッファーのサイズ (ワイド文字)。</span><span class="sxs-lookup"><span data-stu-id="be85e-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="be85e-110">[アウト]返されたバッファーの長さ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="be85e-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="be85e-111">[in] CLSID_RESOLUTION_FLAGS値の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="be85e-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="be85e-112">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="be85e-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="be85e-113">CLSID_RESOLUTION_DEFAULT: (0x0) 既定の相互運用動作を使用することを指定します。</span><span class="sxs-lookup"><span data-stu-id="be85e-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="be85e-114">CLSID_RESOLUTION_REGISTERED: (0x1) レジストリを検索し、shim ポリシーを適用する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="be85e-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be85e-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="be85e-115">Return Value</span></span>  
  
|<span data-ttu-id="be85e-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="be85e-116">HRESULT</span></span>|<span data-ttu-id="be85e-117">説明</span><span class="sxs-lookup"><span data-stu-id="be85e-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="be85e-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="be85e-118">S_OK</span></span>|<span data-ttu-id="be85e-119">関数が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="be85e-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="be85e-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="be85e-120">E_INVALIDARG</span></span>|<span data-ttu-id="be85e-121">パラメータの 1 つに無効な型または形式があります。</span><span class="sxs-lookup"><span data-stu-id="be85e-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="be85e-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="be85e-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="be85e-123">バッファー`pVersion`の大きさが、バージョン文字列全体を保持するのに十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="be85e-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="be85e-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="be85e-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="be85e-125">指定された`CLSID`に登録されているクラスがありません。</span><span class="sxs-lookup"><span data-stu-id="be85e-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="be85e-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="be85e-126">E_POINTER</span></span>|<span data-ttu-id="be85e-127">`dwLength`は null`cchBuffer`であるか、バージョン文字列を保持するのに十分な`pVersion`大きさですが、null です。</span><span class="sxs-lookup"><span data-stu-id="be85e-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be85e-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="be85e-128">Requirements</span></span>  
 <span data-ttu-id="be85e-129">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be85e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be85e-130">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="be85e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be85e-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be85e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be85e-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="be85e-132">See also</span></span>

- [<span data-ttu-id="be85e-133">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="be85e-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
