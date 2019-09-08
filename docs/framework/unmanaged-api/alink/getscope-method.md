---
title: GetScope メソッド
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3a0e42e9ffb99896bdd09dbbab65eafb40cafff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777211"
---
# <a name="getscope-method"></a><span data-ttu-id="da14b-102">GetScope メソッド</span><span class="sxs-lookup"><span data-stu-id="da14b-102">GetScope Method</span></span>
<span data-ttu-id="da14b-103">インポートスコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="da14b-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da14b-104">構文</span><span class="sxs-lookup"><span data-stu-id="da14b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="da14b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da14b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="da14b-106">インポート先のアセンブリの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="da14b-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="da14b-107">インポート元のファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="da14b-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="da14b-108">インポートする0から始まるスコープ。</span><span class="sxs-lookup"><span data-stu-id="da14b-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="da14b-109">スコープの[IMetaDataImport インターフェイス](../metadata/imetadataimport-interface.md)インターフェイスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="da14b-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da14b-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="da14b-110">Return Value</span></span>  
 <span data-ttu-id="da14b-111">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="da14b-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da14b-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="da14b-112">Requirements</span></span>  
 <span data-ttu-id="da14b-113">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="da14b-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da14b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="da14b-114">See also</span></span>

- [<span data-ttu-id="da14b-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da14b-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="da14b-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da14b-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="da14b-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="da14b-117">ALink API</span></span>](index.md)
