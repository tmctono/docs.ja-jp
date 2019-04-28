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
ms.openlocfilehash: 571612796d4e66be9dd8469d748c2380c839ddfa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789819"
---
# <a name="getscope-method"></a><span data-ttu-id="a800e-102">GetScope メソッド</span><span class="sxs-lookup"><span data-stu-id="a800e-102">GetScope Method</span></span>
<span data-ttu-id="a800e-103">インポート スコープを取得します。</span><span class="sxs-lookup"><span data-stu-id="a800e-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a800e-104">構文</span><span class="sxs-lookup"><span data-stu-id="a800e-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a800e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a800e-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a800e-106">インポート先のアセンブリの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="a800e-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a800e-107">インポートするファイルの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="a800e-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="a800e-108">インポートする 0 から始まるスコープです。</span><span class="sxs-lookup"><span data-stu-id="a800e-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="a800e-109">受信[IMetaDataImport インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)スコープのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a800e-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a800e-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="a800e-110">Return Value</span></span>  
 <span data-ttu-id="a800e-111">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="a800e-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a800e-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a800e-112">Requirements</span></span>  
 <span data-ttu-id="a800e-113">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="a800e-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a800e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="a800e-114">See also</span></span>

- [<span data-ttu-id="a800e-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a800e-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a800e-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a800e-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a800e-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="a800e-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
