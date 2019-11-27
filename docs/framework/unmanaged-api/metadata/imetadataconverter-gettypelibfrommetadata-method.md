---
title: IMetaDataConverter::GetTypeLibFromMetaData メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: 9da4e34fa948db2fc73cbde813bac9b3430605ca
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436249"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="9d281-102">IMetaDataConverter::GetTypeLibFromMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="9d281-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="9d281-103">指定されたライブラリ名とモジュール名を持つタイプライブラリを表す `ITypeLib` インスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="9d281-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d281-104">構文</span><span class="sxs-lookup"><span data-stu-id="9d281-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d281-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9d281-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="9d281-106">からタイプライブラリのモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="9d281-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="9d281-107">からタイプライブラリの名前。</span><span class="sxs-lookup"><span data-stu-id="9d281-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="9d281-108">入出力タイプライブラリを表す `ITypeLib` インスタンスのアドレスを受け取る場所へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9d281-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d281-109">要件</span><span class="sxs-lookup"><span data-stu-id="9d281-109">Requirements</span></span>  
 <span data-ttu-id="9d281-110">**プラットフォーム:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d281-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d281-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="9d281-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d281-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="9d281-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d281-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d281-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d281-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d281-114">See also</span></span>

- [<span data-ttu-id="9d281-115">IMetaDataConverter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9d281-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
