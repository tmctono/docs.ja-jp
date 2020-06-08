---
title: IMetaDataConverter インターフェイス
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: 7a2a5080872f49a84e36c53ac337d91738c15e45
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501340"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="a4cae-102">IMetaDataConverter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a4cae-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="a4cae-103">タイプ ライブラリをそれぞれのメタデータ署名にマップして、一方から他方に変換するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="a4cae-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4cae-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a4cae-104">Methods</span></span>  
  
|<span data-ttu-id="a4cae-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a4cae-105">Method</span></span>|<span data-ttu-id="a4cae-106">説明</span><span class="sxs-lookup"><span data-stu-id="a4cae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4cae-107">GetMetaDataFromTypeInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="a4cae-107">GetMetaDataFromTypeInfo Method</span></span>](imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="a4cae-108">指定したインスタンスによって参照されるタイプライブラリのメタデータシグネチャを表す[IMetaDataImport](imetadataimport-interface.md)インスタンスへのポインターを取得し `ITypeInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="a4cae-108">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="a4cae-109">GetMetaDataFromTypeLib メソッド</span><span class="sxs-lookup"><span data-stu-id="a4cae-109">GetMetaDataFromTypeLib Method</span></span>](imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="a4cae-110">`IMetaDataImport`指定したインスタンスによって表されるタイプライブラリのメタデータ署名を表すインスタンスへのポインターを取得し `ITypeLib` ます。</span><span class="sxs-lookup"><span data-stu-id="a4cae-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="a4cae-111">GetTypeLibFromMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="a4cae-111">GetTypeLibFromMetaData Method</span></span>](imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="a4cae-112">指定した `ITypeLib` モジュール名およびライブラリ名を持つタイプライブラリを表すインスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="a4cae-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4cae-113">要件</span><span class="sxs-lookup"><span data-stu-id="a4cae-113">Requirements</span></span>  
 <span data-ttu-id="a4cae-114">**プラットフォーム:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4cae-114">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4cae-115">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="a4cae-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4cae-116">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="a4cae-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4cae-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4cae-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4cae-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4cae-118">See also</span></span>

- [<span data-ttu-id="a4cae-119">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a4cae-119">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="a4cae-120">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a4cae-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
