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
ms.openlocfilehash: 3ab24ab869e1f2cff9beafe50e6982ba2e7cf0aa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436695"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="37f97-102">IMetaDataImport::GetTypeSpecFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="37f97-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="37f97-103">指定したトークンが表すタイプ仕様のバイナリ メタデータ シグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="37f97-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37f97-104">構文</span><span class="sxs-lookup"><span data-stu-id="37f97-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37f97-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="37f97-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="37f97-106">から要求されたメタデータ署名に関連付けられている TypeSpec トークン。</span><span class="sxs-lookup"><span data-stu-id="37f97-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="37f97-107">入出力バイナリメタデータシグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="37f97-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="37f97-108">入出力メタデータシグネチャのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="37f97-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37f97-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="37f97-109">Return Value</span></span>  
 <span data-ttu-id="37f97-110">成功または失敗を示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="37f97-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="37f97-111">失敗したマクロを使用してエラーをテストできます。</span><span class="sxs-lookup"><span data-stu-id="37f97-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37f97-112">要件</span><span class="sxs-lookup"><span data-stu-id="37f97-112">Requirements</span></span>  
 <span data-ttu-id="37f97-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37f97-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37f97-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="37f97-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37f97-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="37f97-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="37f97-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37f97-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37f97-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="37f97-117">See also</span></span>

- [<span data-ttu-id="37f97-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="37f97-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="37f97-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="37f97-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
