---
title: IMetaDataImport::GetNativeCallConvFromSig メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNativeCallConvFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef1ac83b383a9f6bbee7f55441d2abfcb081afa6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122747"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="49861-102">IMetaDataImport::GetNativeCallConvFromSig メソッド</span><span class="sxs-lookup"><span data-stu-id="49861-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="49861-103">指定したシグネチャ ポインターで表されるメソッドのネイティブな呼び出し規約を取得します。</span><span class="sxs-lookup"><span data-stu-id="49861-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49861-104">構文</span><span class="sxs-lookup"><span data-stu-id="49861-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49861-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="49861-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="49861-106">[in]呼び出し規約を返すメソッドのメタデータ署名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="49861-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="49861-107">[in]バイト サイズ`pvSig`します。</span><span class="sxs-lookup"><span data-stu-id="49861-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="49861-108">[out]ネイティブ呼び出し規約へのポインター。</span><span class="sxs-lookup"><span data-stu-id="49861-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49861-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="49861-109">Requirements</span></span>  
 <span data-ttu-id="49861-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49861-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49861-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="49861-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49861-112">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="49861-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49861-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49861-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49861-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="49861-114">See also</span></span>

- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="49861-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="49861-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="49861-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="49861-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
