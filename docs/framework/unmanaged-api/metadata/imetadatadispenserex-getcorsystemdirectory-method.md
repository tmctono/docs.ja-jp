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
ms.openlocfilehash: a76c17e663fdf6555ed878cca1b86b6a9395730e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008795"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="056a6-102">IMetaDataDispenserEx::GetCORSystemDirectory メソッド</span><span class="sxs-lookup"><span data-stu-id="056a6-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="056a6-103">現在の共通言語ランタイム (CLR) が格納されているディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="056a6-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="056a6-104">このメソッドは、アウトプロセスデバッガーでの使用に対してのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="056a6-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="056a6-105">別のコンポーネントから呼び出された場合は、E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="056a6-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="056a6-106">構文</span><span class="sxs-lookup"><span data-stu-id="056a6-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="056a6-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="056a6-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="056a6-108">入出力ディレクトリ名を受け取るバッファー。</span><span class="sxs-lookup"><span data-stu-id="056a6-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="056a6-109">からのサイズ (バイト単位) `szBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="056a6-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="056a6-110">入出力実際にで返されたバイト数 `szBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="056a6-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="056a6-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="056a6-111">Requirements</span></span>  
 <span data-ttu-id="056a6-112">**プラットフォーム:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="056a6-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="056a6-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="056a6-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="056a6-114">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="056a6-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="056a6-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="056a6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="056a6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="056a6-116">See also</span></span>

- [<span data-ttu-id="056a6-117">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="056a6-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="056a6-118">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="056a6-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
