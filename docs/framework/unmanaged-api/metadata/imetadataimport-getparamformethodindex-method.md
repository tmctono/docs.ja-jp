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
ms.openlocfilehash: fdb3def9574f4442a22b370323dfdf044170542b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778946"
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="dfdae-102">IMetaDataImport::GetParamForMethodIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="dfdae-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="dfdae-103">指定した MethodDef トークンによって表されるメソッドの指定されたパラメーターを表すトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="dfdae-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfdae-104">構文</span><span class="sxs-lookup"><span data-stu-id="dfdae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfdae-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dfdae-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="dfdae-106">[in]パラメーターのトークンを返すメソッドを表すトークンです。</span><span class="sxs-lookup"><span data-stu-id="dfdae-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="dfdae-107">[in]要求されたパラメーターが発生したパラメーター リスト内の序数位置。</span><span class="sxs-lookup"><span data-stu-id="dfdae-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="dfdae-108">パラメーターは、メソッドの戻り値の位置は 0 で、1 から始まる番号が付けられます。</span><span class="sxs-lookup"><span data-stu-id="dfdae-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="dfdae-109">[out]要求されたパラメーターを表す ParamDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="dfdae-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfdae-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="dfdae-110">Requirements</span></span>  
 <span data-ttu-id="dfdae-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfdae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfdae-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dfdae-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dfdae-113">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="dfdae-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dfdae-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfdae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfdae-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfdae-115">See also</span></span>

- [<span data-ttu-id="dfdae-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dfdae-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dfdae-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dfdae-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
