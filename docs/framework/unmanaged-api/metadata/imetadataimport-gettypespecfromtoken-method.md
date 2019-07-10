---
title: IMetaDataImport::GetTypeSpecFromToken メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeSpecFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e7e060d2f72609b470dbd5060746a1458f5eed9d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782308"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="04c55-102">IMetaDataImport::GetTypeSpecFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="04c55-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="04c55-103">指定したトークンが表すタイプ仕様のバイナリ メタデータ シグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="04c55-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c55-104">構文</span><span class="sxs-lookup"><span data-stu-id="04c55-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04c55-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04c55-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="04c55-106">[in]要求されたメタデータ署名に関連付けられている TypeSpec トークンです。</span><span class="sxs-lookup"><span data-stu-id="04c55-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="04c55-107">[out]バイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="04c55-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="04c55-108">[out]メタデータのシグネチャのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="04c55-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04c55-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="04c55-109">Return Value</span></span>  
 <span data-ttu-id="04c55-110">成功または失敗を示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="04c55-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="04c55-111">FAILED マクロでは、エラーをテストできます。</span><span class="sxs-lookup"><span data-stu-id="04c55-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04c55-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="04c55-112">Requirements</span></span>  
 <span data-ttu-id="04c55-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04c55-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04c55-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="04c55-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="04c55-115">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="04c55-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="04c55-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04c55-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04c55-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="04c55-117">See also</span></span>

- [<span data-ttu-id="04c55-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="04c55-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="04c55-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="04c55-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
