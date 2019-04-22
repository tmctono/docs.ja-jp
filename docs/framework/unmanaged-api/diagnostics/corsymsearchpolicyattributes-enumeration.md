---
title: CorSymSearchPolicyAttributes 列挙体
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8a9b0f085820bac12638c0310ab23b2eafacb23b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186174"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="c6ab6-102">CorSymSearchPolicyAttributes 列挙体</span><span class="sxs-lookup"><span data-stu-id="c6ab6-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="c6ab6-103">シンボル リーダーの検索を行うときに使用されるポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6ab6-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="c6ab6-104">これらの定数を使って、 [isymunmanagedbinder 2::getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)と[isymunmanagedbinder 3::getreaderfromcallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c6ab6-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c6ab6-105">信頼できないソースからプログラム データベース (PDB) ファイルをセキュリティ リスクになります。</span><span class="sxs-lookup"><span data-stu-id="c6ab6-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6ab6-106">構文</span><span class="sxs-lookup"><span data-stu-id="c6ab6-106">Syntax</span></span>  
  
```  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="c6ab6-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="c6ab6-107">Members</span></span>  
  
|<span data-ttu-id="c6ab6-108">メンバー</span><span class="sxs-lookup"><span data-stu-id="c6ab6-108">Member</span></span>|<span data-ttu-id="c6ab6-109">説明</span><span class="sxs-lookup"><span data-stu-id="c6ab6-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="c6ab6-110">シンボルの検索パスのレジストリを照会します。</span><span class="sxs-lookup"><span data-stu-id="c6ab6-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="c6ab6-111">シンボル サーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c6ab6-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="c6ab6-112">デバッグ ディレクトリで指定されたパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="c6ab6-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="c6ab6-113">.Exe ファイルのある場所に PDB を検索します。</span><span class="sxs-lookup"><span data-stu-id="c6ab6-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6ab6-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="c6ab6-114">Requirements</span></span>  
 <span data-ttu-id="c6ab6-115">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c6ab6-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ab6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6ab6-116">See also</span></span>

- [<span data-ttu-id="c6ab6-117">シンボル ストア診断列挙型</span><span class="sxs-lookup"><span data-stu-id="c6ab6-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
