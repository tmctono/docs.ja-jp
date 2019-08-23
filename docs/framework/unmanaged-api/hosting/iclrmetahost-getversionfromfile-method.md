---
title: ICLRMetaHost::GetVersionFromFile メソッド
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd5d2e820bd1d733bb4ab968a89174124bc91357
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962935"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="5f5c6-102">ICLRMetaHost::GetVersionFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="5f5c6-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="5f5c6-103">ファイルパスを指定して、アセンブリの元の .NET Framework コンパイルバージョン (メタデータに格納されている) を取得します。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="5f5c6-104">このメソッドは、 [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)関数よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f5c6-105">構文</span><span class="sxs-lookup"><span data-stu-id="5f5c6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f5c6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f5c6-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="5f5c6-107">から完全なアセンブリファイルパス。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="5f5c6-108">入出力メタデータに格納されている .NET Framework のコンパイルバージョン。 "v*A と*いう形式になります。*B*[.*X*] "</span><span class="sxs-lookup"><span data-stu-id="5f5c6-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="5f5c6-109">*A*、 *B*、および*X*は、メジャーバージョン、マイナーバージョン、およびビルド番号に対応する10進数です。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="5f5c6-110">この文字列の長さは MAX_PATH に制限されています。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f5c6-111">この出力は、C:\Windows\Microsoft.NET\Framework. の下に表示される .NET Framework バージョンのディレクトリ名と一致します。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="5f5c6-112">値の例としては、"v v1.0.3705"、"v 1.1.4322"、"v v2.0.50727"、および "v4.0" があります。*X*"。ここで*x*は、インストールされているビルド番号に依存します。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="5f5c6-113">"V" プレフィックスが必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="5f5c6-114">[入力、出力]バッファーオーバーランを`pwzbuffer`回避するためののサイズ。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f5c6-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="5f5c6-115">Return Value</span></span>  
 <span data-ttu-id="5f5c6-116">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5f5c6-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f5c6-117">HRESULT</span></span>|<span data-ttu-id="5f5c6-118">説明</span><span class="sxs-lookup"><span data-stu-id="5f5c6-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f5c6-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f5c6-119">S_OK</span></span>|<span data-ttu-id="5f5c6-120">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="5f5c6-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="5f5c6-121">E_POINTER</span></span>|<span data-ttu-id="5f5c6-122">`pwzbuffer` または `pcchBuffer` が null です。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="5f5c6-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="5f5c6-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="5f5c6-124">バッファーが小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f5c6-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="5f5c6-125">Requirements</span></span>  
 <span data-ttu-id="5f5c6-126">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f5c6-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f5c6-127">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="5f5c6-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5f5c6-128">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5f5c6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f5c6-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f5c6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f5c6-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f5c6-130">See also</span></span>

- [<span data-ttu-id="5f5c6-131">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5f5c6-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="5f5c6-132">ホスティング</span><span class="sxs-lookup"><span data-stu-id="5f5c6-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
