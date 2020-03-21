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
ms.openlocfilehash: fb673666543bea3df44005ee3b20d311524f51d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175916"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="d5fb4-102">IMetaDataDispenserEx::GetCORSystemDirectory メソッド</span><span class="sxs-lookup"><span data-stu-id="d5fb4-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="d5fb4-103">現在の共通言語ランタイム (CLR) を保持するディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="d5fb4-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="d5fb4-104">このメソッドは、アウトプロセス デバッガーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5fb4-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="d5fb4-105">別のコンポーネントから呼び出された場合、E_NOTIMPL返します。</span><span class="sxs-lookup"><span data-stu-id="d5fb4-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5fb4-106">構文</span><span class="sxs-lookup"><span data-stu-id="d5fb4-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5fb4-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5fb4-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="d5fb4-108">[アウト]ディレクトリ名を受け取るバッファ。</span><span class="sxs-lookup"><span data-stu-id="d5fb4-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="d5fb4-109">[in]のサイズ (バイト単位)`szBuffer`です。</span><span class="sxs-lookup"><span data-stu-id="d5fb4-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="d5fb4-110">[アウト]で実際に返される`szBuffer`バイト数。</span><span class="sxs-lookup"><span data-stu-id="d5fb4-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5fb4-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d5fb4-111">Requirements</span></span>  
 <span data-ttu-id="d5fb4-112">**プラットフォーム:**[「システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5fb4-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5fb4-113">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="d5fb4-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d5fb4-114">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d5fb4-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d5fb4-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5fb4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5fb4-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5fb4-116">See also</span></span>

- [<span data-ttu-id="d5fb4-117">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5fb4-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="d5fb4-118">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d5fb4-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
