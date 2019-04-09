---
title: CVStruct 構造体
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a5f06b3f79fed5dac5a6f07650e4fabd0aa5867
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142169"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="8f4d1-102">CVStruct 構造体</span><span class="sxs-lookup"><span data-stu-id="8f4d1-102">CVStruct Structure</span></span>
<span data-ttu-id="8f4d1-103">モジュールまたは複合イメージをインストールするときに使用する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f4d1-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f4d1-104">構文</span><span class="sxs-lookup"><span data-stu-id="8f4d1-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="8f4d1-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="8f4d1-105">Members</span></span>  
  
|<span data-ttu-id="8f4d1-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="8f4d1-106">Member</span></span>|<span data-ttu-id="8f4d1-107">説明</span><span class="sxs-lookup"><span data-stu-id="8f4d1-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8f4d1-108">Major</span><span class="sxs-lookup"><span data-stu-id="8f4d1-108">Major</span></span>|<span data-ttu-id="8f4d1-109">ビルド番号のメジャー バージョンです。</span><span class="sxs-lookup"><span data-stu-id="8f4d1-109">Major version build number.</span></span>|  
|<span data-ttu-id="8f4d1-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="8f4d1-110">Minor</span></span>|<span data-ttu-id="8f4d1-111">ビルド番号のマイナー バージョンです。</span><span class="sxs-lookup"><span data-stu-id="8f4d1-111">Minor version build number.</span></span>|  
|<span data-ttu-id="8f4d1-112">Sub</span><span class="sxs-lookup"><span data-stu-id="8f4d1-112">Sub</span></span>|<span data-ttu-id="8f4d1-113">サブ ビルド番号です。</span><span class="sxs-lookup"><span data-stu-id="8f4d1-113">Sub-build number.</span></span>|  
|<span data-ttu-id="8f4d1-114">ビルド</span><span class="sxs-lookup"><span data-stu-id="8f4d1-114">Build</span></span>|<span data-ttu-id="8f4d1-115">ビルド番号です。</span><span class="sxs-lookup"><span data-stu-id="8f4d1-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f4d1-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="8f4d1-116">Requirements</span></span>  
 <span data-ttu-id="8f4d1-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f4d1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f4d1-118">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8f4d1-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f4d1-119">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="8f4d1-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8f4d1-120">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8f4d1-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f4d1-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f4d1-121">See also</span></span>

- [<span data-ttu-id="8f4d1-122">メタデータ構造体</span><span class="sxs-lookup"><span data-stu-id="8f4d1-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
