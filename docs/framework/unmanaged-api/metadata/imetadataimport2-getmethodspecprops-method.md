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
ms.openlocfilehash: 6b5b3b3b5a3613668f4470f48083ae010cc9d336
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445254"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="898e9-102">IMetaDataImport2::GetMethodSpecProps メソッド</span><span class="sxs-lookup"><span data-stu-id="898e9-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="898e9-103">指定した MethodSpec トークンによって参照されるメソッドのメタデータシグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="898e9-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="898e9-104">構文</span><span class="sxs-lookup"><span data-stu-id="898e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="898e9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="898e9-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="898e9-106">からメソッドのインスタンス化を表す MethodSpec トークン。</span><span class="sxs-lookup"><span data-stu-id="898e9-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="898e9-107">入出力メソッド定義を表す MethodDef または MethodRef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="898e9-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="898e9-108">入出力メソッドのバイナリメタデータシグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="898e9-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="898e9-109">入出力`ppvSigBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="898e9-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="898e9-110">要件</span><span class="sxs-lookup"><span data-stu-id="898e9-110">Requirements</span></span>  
 <span data-ttu-id="898e9-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="898e9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="898e9-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="898e9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="898e9-113">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="898e9-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="898e9-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="898e9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="898e9-115">参照</span><span class="sxs-lookup"><span data-stu-id="898e9-115">See also</span></span>

- [<span data-ttu-id="898e9-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="898e9-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="898e9-117">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="898e9-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
