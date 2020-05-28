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
ms.openlocfilehash: 84791eba7c95d3278bd4650bd7d660e98fcb79d8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008920"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="790a6-102">CVStruct 構造体</span><span class="sxs-lookup"><span data-stu-id="790a6-102">CVStruct Structure</span></span>
<span data-ttu-id="790a6-103">モジュールまたは複合イメージをインストールするときに使用する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="790a6-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="790a6-104">構文</span><span class="sxs-lookup"><span data-stu-id="790a6-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="790a6-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="790a6-105">Members</span></span>  
  
|<span data-ttu-id="790a6-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="790a6-106">Member</span></span>|<span data-ttu-id="790a6-107">説明</span><span class="sxs-lookup"><span data-stu-id="790a6-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="790a6-108">メジャー</span><span class="sxs-lookup"><span data-stu-id="790a6-108">Major</span></span>|<span data-ttu-id="790a6-109">メジャーバージョンのビルド番号。</span><span class="sxs-lookup"><span data-stu-id="790a6-109">Major version build number.</span></span>|  
|<span data-ttu-id="790a6-110">Minor</span><span class="sxs-lookup"><span data-stu-id="790a6-110">Minor</span></span>|<span data-ttu-id="790a6-111">マイナーバージョンのビルド番号。</span><span class="sxs-lookup"><span data-stu-id="790a6-111">Minor version build number.</span></span>|  
|<span data-ttu-id="790a6-112">Sub</span><span class="sxs-lookup"><span data-stu-id="790a6-112">Sub</span></span>|<span data-ttu-id="790a6-113">サブビルド番号。</span><span class="sxs-lookup"><span data-stu-id="790a6-113">Sub-build number.</span></span>|  
|<span data-ttu-id="790a6-114">Build</span><span class="sxs-lookup"><span data-stu-id="790a6-114">Build</span></span>|<span data-ttu-id="790a6-115">ビルド番号。</span><span class="sxs-lookup"><span data-stu-id="790a6-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="790a6-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="790a6-116">Requirements</span></span>  
 <span data-ttu-id="790a6-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="790a6-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="790a6-118">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="790a6-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="790a6-119">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="790a6-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="790a6-120">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="790a6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790a6-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="790a6-121">See also</span></span>

- [<span data-ttu-id="790a6-122">メタデータ構造体</span><span class="sxs-lookup"><span data-stu-id="790a6-122">Metadata Structures</span></span>](metadata-structures.md)
