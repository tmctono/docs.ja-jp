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
ms.openlocfilehash: 5e36cb91c3ef741badb04b54e2b62158ecf6ced1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134499"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="11199-102">CorMethodSemanticsAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="11199-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="11199-103">メソッドとそれに関連付けられているプロパティまたはイベントとの関係を記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="11199-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11199-104">構文</span><span class="sxs-lookup"><span data-stu-id="11199-104">Syntax</span></span>  
  
```  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="11199-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="11199-105">Members</span></span>  
  
|<span data-ttu-id="11199-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="11199-106">Member</span></span>|<span data-ttu-id="11199-107">説明</span><span class="sxs-lookup"><span data-stu-id="11199-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="11199-108">メソッドを指定します、`set`プロパティのアクセサー。</span><span class="sxs-lookup"><span data-stu-id="11199-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="11199-109">メソッドを指定します、`get`プロパティのアクセサー。</span><span class="sxs-lookup"><span data-stu-id="11199-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="11199-110">メソッドに、プロパティまたはここで定義されているもの以外のイベントへのリレーションシップを指定します。</span><span class="sxs-lookup"><span data-stu-id="11199-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="11199-111">メソッドがイベント ハンドラー メソッドを追加指定します。</span><span class="sxs-lookup"><span data-stu-id="11199-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="11199-112">メソッドがイベント ハンドラー メソッドを削除するを指定します。</span><span class="sxs-lookup"><span data-stu-id="11199-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="11199-113">メソッドがイベントを発生させることを指定します。</span><span class="sxs-lookup"><span data-stu-id="11199-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11199-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="11199-114">Requirements</span></span>  
 <span data-ttu-id="11199-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="11199-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11199-116">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="11199-116">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="11199-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="11199-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11199-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="11199-118">See also</span></span>

- [<span data-ttu-id="11199-119">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="11199-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
