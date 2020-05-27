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
ms.openlocfilehash: 79bd8901641ee587e94861c0aec85b812591ea48
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008418"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="b7285-102">IMetaDataConverter::GetTypeLibFromMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="b7285-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="b7285-103">指定した `ITypeLib` ライブラリ名とモジュール名を持つタイプライブラリを表すインスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="b7285-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7285-104">構文</span><span class="sxs-lookup"><span data-stu-id="b7285-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7285-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b7285-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="b7285-106">からタイプライブラリのモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="b7285-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="b7285-107">からタイプライブラリの名前。</span><span class="sxs-lookup"><span data-stu-id="b7285-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="b7285-108">入出力タイプライブラリを表すインスタンスのアドレスを受け取る場所へのポインター `ITypeLib` 。</span><span class="sxs-lookup"><span data-stu-id="b7285-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7285-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="b7285-109">Requirements</span></span>  
 <span data-ttu-id="b7285-110">**プラットフォーム:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7285-110">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7285-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="b7285-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7285-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="b7285-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b7285-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7285-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7285-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7285-114">See also</span></span>

- [<span data-ttu-id="b7285-115">IMetaDataConverter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7285-115">IMetaDataConverter Interface</span></span>](imetadataconverter-interface.md)
