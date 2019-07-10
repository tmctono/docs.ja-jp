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
ms.openlocfilehash: b3e35cea4601c8e51eb3021dc9f598ddb881afe0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750723"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="68de4-102">CVStruct 構造体</span><span class="sxs-lookup"><span data-stu-id="68de4-102">CVStruct Structure</span></span>
<span data-ttu-id="68de4-103">モジュールまたは複合イメージをインストールするときに使用する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="68de4-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68de4-104">構文</span><span class="sxs-lookup"><span data-stu-id="68de4-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="68de4-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="68de4-105">Members</span></span>  
  
|<span data-ttu-id="68de4-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="68de4-106">Member</span></span>|<span data-ttu-id="68de4-107">説明</span><span class="sxs-lookup"><span data-stu-id="68de4-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="68de4-108">Major</span><span class="sxs-lookup"><span data-stu-id="68de4-108">Major</span></span>|<span data-ttu-id="68de4-109">ビルド番号のメジャー バージョンです。</span><span class="sxs-lookup"><span data-stu-id="68de4-109">Major version build number.</span></span>|  
|<span data-ttu-id="68de4-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="68de4-110">Minor</span></span>|<span data-ttu-id="68de4-111">ビルド番号のマイナー バージョンです。</span><span class="sxs-lookup"><span data-stu-id="68de4-111">Minor version build number.</span></span>|  
|<span data-ttu-id="68de4-112">Sub</span><span class="sxs-lookup"><span data-stu-id="68de4-112">Sub</span></span>|<span data-ttu-id="68de4-113">サブ ビルド番号です。</span><span class="sxs-lookup"><span data-stu-id="68de4-113">Sub-build number.</span></span>|  
|<span data-ttu-id="68de4-114">Build</span><span class="sxs-lookup"><span data-stu-id="68de4-114">Build</span></span>|<span data-ttu-id="68de4-115">ビルド番号です。</span><span class="sxs-lookup"><span data-stu-id="68de4-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68de4-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="68de4-116">Requirements</span></span>  
 <span data-ttu-id="68de4-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68de4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68de4-118">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="68de4-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="68de4-119">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="68de4-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="68de4-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68de4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68de4-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="68de4-121">See also</span></span>

- [<span data-ttu-id="68de4-122">メタデータ構造体</span><span class="sxs-lookup"><span data-stu-id="68de4-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
