---
title: IMetaDataEmit::DefineSecurityAttributeSet メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f7c5378490dce93599086819ee6fc806c707aa2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777495"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="a4180-102">IMetaDataEmit::DefineSecurityAttributeSet メソッド</span><span class="sxs-lookup"><span data-stu-id="a4180-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="a4180-103">指定したトークンによって参照されるオブジェクトにアタッチするセキュリティ権限のセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="a4180-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4180-104">構文</span><span class="sxs-lookup"><span data-stu-id="a4180-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4180-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a4180-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="a4180-106">[in]セキュリティ情報が接続されているトークンです。</span><span class="sxs-lookup"><span data-stu-id="a4180-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="a4180-107">[in]配列の`COR_SECATTR`構造体。</span><span class="sxs-lookup"><span data-stu-id="a4180-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="a4180-108">[in]要素数`rSecAttrs`します。</span><span class="sxs-lookup"><span data-stu-id="a4180-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="a4180-109">[out]メソッドが失敗した場合にインデックスを指定します。`rSecAttrs`の問題の原因となった要素。</span><span class="sxs-lookup"><span data-stu-id="a4180-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4180-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a4180-110">Requirements</span></span>  
 <span data-ttu-id="a4180-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4180-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4180-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a4180-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4180-113">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="a4180-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4180-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4180-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4180-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4180-115">See also</span></span>

- [<span data-ttu-id="a4180-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a4180-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a4180-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a4180-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
