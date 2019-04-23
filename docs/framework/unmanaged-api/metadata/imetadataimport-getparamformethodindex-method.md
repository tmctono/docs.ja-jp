---
title: IMetaDataImport::GetParamForMethodIndex メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamForMethodIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7c6f06ff4fc7d855ea07f1f572a2b7ea948efc51
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207059"
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="e0c36-102">IMetaDataImport::GetParamForMethodIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="e0c36-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="e0c36-103">指定した MethodDef トークンによって表されるメソッドの指定されたパラメーターを表すトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="e0c36-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c36-104">構文</span><span class="sxs-lookup"><span data-stu-id="e0c36-104">Syntax</span></span>  
  
```  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0c36-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0c36-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="e0c36-106">[in]パラメーターのトークンを返すメソッドを表すトークンです。</span><span class="sxs-lookup"><span data-stu-id="e0c36-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="e0c36-107">[in]要求されたパラメーターが発生したパラメーター リスト内の序数位置。</span><span class="sxs-lookup"><span data-stu-id="e0c36-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="e0c36-108">パラメーターは、メソッドの戻り値の位置は 0 で、1 から始まる番号が付けられます。</span><span class="sxs-lookup"><span data-stu-id="e0c36-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="e0c36-109">[out]要求されたパラメーターを表す ParamDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e0c36-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0c36-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="e0c36-110">Requirements</span></span>  
 <span data-ttu-id="e0c36-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0c36-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0c36-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e0c36-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e0c36-113">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e0c36-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e0c36-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0c36-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c36-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0c36-115">See also</span></span>

- [<span data-ttu-id="e0c36-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0c36-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e0c36-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0c36-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
