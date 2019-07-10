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
ms.openlocfilehash: f03a2dfa60f2fbdce317d96a9e5b23c6f017dc3d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777742"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="6503d-102">IMetaDataDispenserEx::GetCORSystemDirectory メソッド</span><span class="sxs-lookup"><span data-stu-id="6503d-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="6503d-103">現在の共通言語ランタイム (CLR) を保持するディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="6503d-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="6503d-104">このメソッドは、プロセス外のデバッガーでのみサポートします。</span><span class="sxs-lookup"><span data-stu-id="6503d-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="6503d-105">別のコンポーネントから呼び出す場合、E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="6503d-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6503d-106">構文</span><span class="sxs-lookup"><span data-stu-id="6503d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6503d-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6503d-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="6503d-108">[out]ディレクトリ名を受け取るバッファー。</span><span class="sxs-lookup"><span data-stu-id="6503d-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="6503d-109">[in]サイズ (バイト単位) の`szBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="6503d-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="6503d-110">[out]実際に返されるバイト数`szBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="6503d-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6503d-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="6503d-111">Requirements</span></span>  
 <span data-ttu-id="6503d-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6503d-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6503d-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6503d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6503d-114">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="6503d-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6503d-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6503d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6503d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6503d-116">See also</span></span>

- [<span data-ttu-id="6503d-117">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6503d-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="6503d-118">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6503d-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
