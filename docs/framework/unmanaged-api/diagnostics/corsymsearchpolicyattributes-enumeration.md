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
ms.openlocfilehash: 7188c516d3d0a5192251697ec743e9d41f8d9072
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913735"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="99ddf-102">CorSymSearchPolicyAttributes 列挙体</span><span class="sxs-lookup"><span data-stu-id="99ddf-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="99ddf-103">シンボルリーダーの検索を実行するときに使用するポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="99ddf-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="99ddf-104">これらの定数は、 [ISymUnmanagedBinder2:: GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)メソッドと[ISymUnmanagedBinder3:: GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)メソッドによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="99ddf-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="99ddf-105">信頼されていないソースからプログラムデータベース (PDB) ファイルを開くと、セキュリティ上の危険があります。</span><span class="sxs-lookup"><span data-stu-id="99ddf-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99ddf-106">構文</span><span class="sxs-lookup"><span data-stu-id="99ddf-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="99ddf-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="99ddf-107">Members</span></span>  
  
|<span data-ttu-id="99ddf-108">メンバー</span><span class="sxs-lookup"><span data-stu-id="99ddf-108">Member</span></span>|<span data-ttu-id="99ddf-109">説明</span><span class="sxs-lookup"><span data-stu-id="99ddf-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="99ddf-110">シンボル検索パスのレジストリを照会します。</span><span class="sxs-lookup"><span data-stu-id="99ddf-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="99ddf-111">シンボルサーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="99ddf-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="99ddf-112">デバッグディレクトリに指定されているパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="99ddf-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="99ddf-113">.Exe ファイルがある場所で PDB を検索します。</span><span class="sxs-lookup"><span data-stu-id="99ddf-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99ddf-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="99ddf-114">Requirements</span></span>  
 <span data-ttu-id="99ddf-115">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="99ddf-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ddf-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="99ddf-116">See also</span></span>

- [<span data-ttu-id="99ddf-117">シンボル ストア診断列挙型</span><span class="sxs-lookup"><span data-stu-id="99ddf-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
