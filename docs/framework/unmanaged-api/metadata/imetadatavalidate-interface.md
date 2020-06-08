---
title: IMetaDataValidate インターフェイス
ms.date: 03/30/2017
api_name:
- IMetaDataValidate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate
helpviewer_keywords:
- IMetaDataValidate interface [.NET Framework metadata]
ms.assetid: db98608a-e85c-4f50-9d7b-5f57a426ddb6
topic_type:
- apiref
ms.openlocfilehash: 2dbd4559bad54aee69f6980e8baf6441480f482c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84489719"
---
# <a name="imetadatavalidate-interface"></a><span data-ttu-id="b5cc5-102">IMetaDataValidate インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b5cc5-102">IMetaDataValidate Interface</span></span>
<span data-ttu-id="b5cc5-103">メタデータ署名を検証するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="b5cc5-103">Provides methods to validate metadata signatures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b5cc5-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="b5cc5-104">Methods</span></span>  
  
|<span data-ttu-id="b5cc5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b5cc5-105">Method</span></span>|<span data-ttu-id="b5cc5-106">説明</span><span class="sxs-lookup"><span data-stu-id="b5cc5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b5cc5-107">ValidateMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="b5cc5-107">ValidateMetaData Method</span></span>](imetadatavalidate-validatemetadata-method.md)|<span data-ttu-id="b5cc5-108">現在のメタデータ スコープ内にあるオブジェクトのメタデータ署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="b5cc5-108">Validates the metadata signatures of the objects in the current metadata scope.</span></span>|  
|[<span data-ttu-id="b5cc5-109">ValidatorInit メソッド</span><span class="sxs-lookup"><span data-stu-id="b5cc5-109">ValidatorInit Method</span></span>](imetadatavalidate-validatorinit-method.md)|<span data-ttu-id="b5cc5-110">現在のメタデータ スコープ内にあるモジュールの種類を指定するフラグを設定し、指定されたコールバック メソッドを検証エラー用に登録します。</span><span class="sxs-lookup"><span data-stu-id="b5cc5-110">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5cc5-111">要件</span><span class="sxs-lookup"><span data-stu-id="b5cc5-111">Requirements</span></span>  
 <span data-ttu-id="b5cc5-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5cc5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5cc5-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="b5cc5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5cc5-114">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5cc5-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5cc5-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5cc5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5cc5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5cc5-116">See also</span></span>

- [<span data-ttu-id="b5cc5-117">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b5cc5-117">Metadata Interfaces</span></span>](metadata-interfaces.md)
