---
title: IMetaDataDispenserEx::GetCORSystemDirectory メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3dbfca942d61cd5667293d11f358f06bd000fa2e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118002"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="86fd0-102">IMetaDataDispenserEx::GetCORSystemDirectory メソッド</span><span class="sxs-lookup"><span data-stu-id="86fd0-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="86fd0-103">現在の共通言語ランタイム (CLR) を保持するディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="86fd0-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="86fd0-104">このメソッドは、プロセス外のデバッガーでのみサポートします。</span><span class="sxs-lookup"><span data-stu-id="86fd0-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="86fd0-105">別のコンポーネントから呼び出す場合、E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="86fd0-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86fd0-106">構文</span><span class="sxs-lookup"><span data-stu-id="86fd0-106">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86fd0-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="86fd0-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="86fd0-108">[out]ディレクトリ名を受け取るバッファー。</span><span class="sxs-lookup"><span data-stu-id="86fd0-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="86fd0-109">[in]サイズ (バイト単位) の`szBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="86fd0-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="86fd0-110">[out]実際に返されるバイト数`szBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="86fd0-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86fd0-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="86fd0-111">Requirements</span></span>  
 <span data-ttu-id="86fd0-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="86fd0-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86fd0-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="86fd0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86fd0-114">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="86fd0-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="86fd0-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="86fd0-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="86fd0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="86fd0-116">See also</span></span>

- [<span data-ttu-id="86fd0-117">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="86fd0-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="86fd0-118">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="86fd0-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
