---
title: CorMethodSemanticsAttr 列挙型
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b09ccfdb33c9853ed97005461f2288f1e7e6fd1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781747"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="4d04b-102">CorMethodSemanticsAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="4d04b-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="4d04b-103">メソッドとそれに関連付けられているプロパティまたはイベントとの関係を記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="4d04b-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d04b-104">構文</span><span class="sxs-lookup"><span data-stu-id="4d04b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="4d04b-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="4d04b-105">Members</span></span>  
  
|<span data-ttu-id="4d04b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="4d04b-106">Member</span></span>|<span data-ttu-id="4d04b-107">説明</span><span class="sxs-lookup"><span data-stu-id="4d04b-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="4d04b-108">メソッドを指定します、`set`プロパティのアクセサー。</span><span class="sxs-lookup"><span data-stu-id="4d04b-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="4d04b-109">メソッドを指定します、`get`プロパティのアクセサー。</span><span class="sxs-lookup"><span data-stu-id="4d04b-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="4d04b-110">メソッドに、プロパティまたはここで定義されているもの以外のイベントへのリレーションシップを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d04b-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="4d04b-111">メソッドがイベント ハンドラー メソッドを追加指定します。</span><span class="sxs-lookup"><span data-stu-id="4d04b-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="4d04b-112">メソッドがイベント ハンドラー メソッドを削除するを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d04b-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="4d04b-113">メソッドがイベントを発生させることを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d04b-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4d04b-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="4d04b-114">Requirements</span></span>  
 <span data-ttu-id="4d04b-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d04b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d04b-116">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4d04b-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4d04b-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d04b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d04b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d04b-118">See also</span></span>

- [<span data-ttu-id="4d04b-119">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="4d04b-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
