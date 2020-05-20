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
ms.openlocfilehash: 0cd451854d4dbb3b243339efdc33d7dcd7860eb7
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420605"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="c6e4d-102">CorSymSearchPolicyAttributes 列挙体</span><span class="sxs-lookup"><span data-stu-id="c6e4d-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="c6e4d-103">シンボルリーダーの検索を実行するときに使用するポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6e4d-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="c6e4d-104">これらの定数は、 [ISymUnmanagedBinder2:: GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)メソッドと[ISymUnmanagedBinder3:: GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md)メソッドによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6e4d-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c6e4d-105">信頼されていないソースからプログラムデータベース (PDB) ファイルを開くと、セキュリティ上の危険があります。</span><span class="sxs-lookup"><span data-stu-id="c6e4d-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6e4d-106">構文</span><span class="sxs-lookup"><span data-stu-id="c6e4d-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="c6e4d-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="c6e4d-107">Members</span></span>  
  
|<span data-ttu-id="c6e4d-108">メンバー</span><span class="sxs-lookup"><span data-stu-id="c6e4d-108">Member</span></span>|<span data-ttu-id="c6e4d-109">説明</span><span class="sxs-lookup"><span data-stu-id="c6e4d-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="c6e4d-110">シンボル検索パスのレジストリを照会します。</span><span class="sxs-lookup"><span data-stu-id="c6e4d-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="c6e4d-111">シンボルサーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c6e4d-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="c6e4d-112">デバッグディレクトリに指定されているパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="c6e4d-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="c6e4d-113">.Exe ファイルがある場所で PDB を検索します。</span><span class="sxs-lookup"><span data-stu-id="c6e4d-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6e4d-114">要件</span><span class="sxs-lookup"><span data-stu-id="c6e4d-114">Requirements</span></span>  
 <span data-ttu-id="c6e4d-115">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="c6e4d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e4d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6e4d-116">See also</span></span>

- [<span data-ttu-id="c6e4d-117">シンボル ストア診断列挙型</span><span class="sxs-lookup"><span data-stu-id="c6e4d-117">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
