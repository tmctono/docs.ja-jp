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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045631"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="cbc80-102">CorMethodSemanticsAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="cbc80-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="cbc80-103">メソッドとそれに関連付けられているプロパティまたはイベントとの関係を記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="cbc80-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbc80-104">構文</span><span class="sxs-lookup"><span data-stu-id="cbc80-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="cbc80-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="cbc80-105">Members</span></span>  
  
|<span data-ttu-id="cbc80-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="cbc80-106">Member</span></span>|<span data-ttu-id="cbc80-107">説明</span><span class="sxs-lookup"><span data-stu-id="cbc80-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="cbc80-108">メソッドを指定します、`set`プロパティのアクセサー。</span><span class="sxs-lookup"><span data-stu-id="cbc80-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="cbc80-109">メソッドを指定します、`get`プロパティのアクセサー。</span><span class="sxs-lookup"><span data-stu-id="cbc80-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="cbc80-110">メソッドに、プロパティまたはここで定義されているもの以外のイベントへのリレーションシップを指定します。</span><span class="sxs-lookup"><span data-stu-id="cbc80-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="cbc80-111">メソッドがイベント ハンドラー メソッドを追加指定します。</span><span class="sxs-lookup"><span data-stu-id="cbc80-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="cbc80-112">メソッドがイベント ハンドラー メソッドを削除するを指定します。</span><span class="sxs-lookup"><span data-stu-id="cbc80-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="cbc80-113">メソッドがイベントを発生させることを指定します。</span><span class="sxs-lookup"><span data-stu-id="cbc80-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cbc80-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="cbc80-114">Requirements</span></span>  
 <span data-ttu-id="cbc80-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbc80-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbc80-116">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="cbc80-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="cbc80-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbc80-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc80-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbc80-118">See also</span></span>

- [<span data-ttu-id="cbc80-119">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="cbc80-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
