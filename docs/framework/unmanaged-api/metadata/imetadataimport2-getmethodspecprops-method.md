---
title: IMetaDataImport2::GetMethodSpecProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetMethodSpecProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7700236efe7b031866867f5ed859ba71683a8a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782293"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="4dad1-102">IMetaDataImport2::GetMethodSpecProps メソッド</span><span class="sxs-lookup"><span data-stu-id="4dad1-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="4dad1-103">指定した MethodSpec によって参照されるメソッドのメタデータ署名のトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="4dad1-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dad1-104">構文</span><span class="sxs-lookup"><span data-stu-id="4dad1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="4dad1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4dad1-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="4dad1-106">[in]メソッドのインスタンス化を表す MethodSpec トークンです。</span><span class="sxs-lookup"><span data-stu-id="4dad1-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="4dad1-107">[out]メソッド定義を表す MethodDef または新しいトークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4dad1-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="4dad1-108">[out]メソッドのバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4dad1-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="4dad1-109">[out]サイズ (バイト単位) の`ppvSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="4dad1-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dad1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="4dad1-110">Requirements</span></span>  
 <span data-ttu-id="4dad1-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dad1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dad1-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4dad1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4dad1-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="4dad1-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4dad1-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dad1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dad1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4dad1-115">See also</span></span>

- [<span data-ttu-id="4dad1-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4dad1-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="4dad1-117">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4dad1-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
