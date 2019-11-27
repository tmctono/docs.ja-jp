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
ms.openlocfilehash: 078168ae8860f18ff6f811dcc972e3eb3c857e1d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447197"
---
# <a name="getscope-method"></a><span data-ttu-id="29a70-102">GetScope メソッド</span><span class="sxs-lookup"><span data-stu-id="29a70-102">GetScope Method</span></span>
<span data-ttu-id="29a70-103">インポートスコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="29a70-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29a70-104">構文</span><span class="sxs-lookup"><span data-stu-id="29a70-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="29a70-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="29a70-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="29a70-106">インポート先のアセンブリの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="29a70-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="29a70-107">インポート元のファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="29a70-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="29a70-108">インポートする0から始まるスコープ。</span><span class="sxs-lookup"><span data-stu-id="29a70-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="29a70-109">スコープの[IMetaDataImport インターフェイス](../metadata/imetadataimport-interface.md)インターフェイスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="29a70-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29a70-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="29a70-110">Return Value</span></span>  
 <span data-ttu-id="29a70-111">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="29a70-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29a70-112">要件</span><span class="sxs-lookup"><span data-stu-id="29a70-112">Requirements</span></span>  
 <span data-ttu-id="29a70-113">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="29a70-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29a70-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="29a70-114">See also</span></span>

- [<span data-ttu-id="29a70-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29a70-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="29a70-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="29a70-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="29a70-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="29a70-117">ALink API</span></span>](index.md)
