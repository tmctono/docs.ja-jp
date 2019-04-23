---
title: OLE DB スキーマ コレクション
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164685"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="e90da-102">OLE DB スキーマ コレクション</span><span class="sxs-lookup"><span data-stu-id="e90da-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="e90da-103">ここでは、Microsoft SQL Server、Oracle、および Microsoft Jet 用の各 OLE DB プロバイダーでのスキーマ コレクションのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e90da-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="e90da-104">Microsoft SQL Server OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="e90da-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="e90da-105">Microsoft SQL Server OLE DB Driver は、共通のスキーマ コレクションに加えて次の特定のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e90da-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e90da-106">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e90da-106">Tables</span></span>  
  
-   <span data-ttu-id="e90da-107">列</span><span class="sxs-lookup"><span data-stu-id="e90da-107">Columns</span></span>  
  
-   <span data-ttu-id="e90da-108">手順</span><span class="sxs-lookup"><span data-stu-id="e90da-108">Procedures</span></span>  
  
-   <span data-ttu-id="e90da-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e90da-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e90da-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="e90da-110">Catalog</span></span>  
  
-   <span data-ttu-id="e90da-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="e90da-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="e90da-112">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e90da-112">Tables</span></span>  
  
|<span data-ttu-id="e90da-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-113">ColumnName</span></span>|<span data-ttu-id="e90da-114">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-115">TABLE_CATALOG</span></span>|<span data-ttu-id="e90da-116">String</span><span class="sxs-lookup"><span data-stu-id="e90da-116">String</span></span>|  
|<span data-ttu-id="e90da-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="e90da-118">String</span><span class="sxs-lookup"><span data-stu-id="e90da-118">String</span></span>|  
|<span data-ttu-id="e90da-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-119">TABLE_NAME</span></span>|<span data-ttu-id="e90da-120">String</span><span class="sxs-lookup"><span data-stu-id="e90da-120">String</span></span>|  
|<span data-ttu-id="e90da-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-121">TABLE_TYPE</span></span>|<span data-ttu-id="e90da-122">String</span><span class="sxs-lookup"><span data-stu-id="e90da-122">String</span></span>|  
|<span data-ttu-id="e90da-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-123">TABLE_GUID</span></span>|<span data-ttu-id="e90da-124">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-124">Guid</span></span>|  
|<span data-ttu-id="e90da-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-125">DESCRIPTION</span></span>|<span data-ttu-id="e90da-126">String</span><span class="sxs-lookup"><span data-stu-id="e90da-126">String</span></span>|  
|<span data-ttu-id="e90da-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="e90da-127">TABLE_PROPID</span></span>|<span data-ttu-id="e90da-128">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-128">Int64</span></span>|  
|<span data-ttu-id="e90da-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e90da-129">DATE_CREATED</span></span>|<span data-ttu-id="e90da-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-130">DateTime</span></span>|  
|<span data-ttu-id="e90da-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e90da-131">DATE_MODIFIED</span></span>|<span data-ttu-id="e90da-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e90da-133">列</span><span class="sxs-lookup"><span data-stu-id="e90da-133">Columns</span></span>  
  
|<span data-ttu-id="e90da-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-134">ColumnName</span></span>|<span data-ttu-id="e90da-135">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-136">TABLE_CATALOG</span></span>|<span data-ttu-id="e90da-137">String</span><span class="sxs-lookup"><span data-stu-id="e90da-137">String</span></span>|  
|<span data-ttu-id="e90da-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="e90da-139">String</span><span class="sxs-lookup"><span data-stu-id="e90da-139">String</span></span>|  
|<span data-ttu-id="e90da-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-140">TABLE_NAME</span></span>|<span data-ttu-id="e90da-141">String</span><span class="sxs-lookup"><span data-stu-id="e90da-141">String</span></span>|  
|<span data-ttu-id="e90da-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-142">COLUMN_NAME</span></span>|<span data-ttu-id="e90da-143">String</span><span class="sxs-lookup"><span data-stu-id="e90da-143">String</span></span>|  
|<span data-ttu-id="e90da-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-144">COLUMN_GUID</span></span>|<span data-ttu-id="e90da-145">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-145">Guid</span></span>|  
|<span data-ttu-id="e90da-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e90da-146">COLUMN_PROPID</span></span>|<span data-ttu-id="e90da-147">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-147">Int64</span></span>|  
|<span data-ttu-id="e90da-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e90da-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="e90da-149">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-149">Int64</span></span>|  
|<span data-ttu-id="e90da-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e90da-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="e90da-151">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-151">Boolean</span></span>|  
|<span data-ttu-id="e90da-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e90da-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="e90da-153">String</span><span class="sxs-lookup"><span data-stu-id="e90da-153">String</span></span>|  
|<span data-ttu-id="e90da-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e90da-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="e90da-155">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-155">Int64</span></span>|  
|<span data-ttu-id="e90da-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e90da-156">IS_NULLABLE</span></span>|<span data-ttu-id="e90da-157">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-157">Boolean</span></span>|  
|<span data-ttu-id="e90da-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-158">DATA_TYPE</span></span>|<span data-ttu-id="e90da-159">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-159">Int32</span></span>|  
|<span data-ttu-id="e90da-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-160">TYPE_GUID</span></span>|<span data-ttu-id="e90da-161">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-161">Guid</span></span>|  
|<span data-ttu-id="e90da-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e90da-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e90da-163">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-163">Int64</span></span>|  
|<span data-ttu-id="e90da-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e90da-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e90da-165">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-165">Int64</span></span>|  
|<span data-ttu-id="e90da-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e90da-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e90da-167">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-167">Int32</span></span>|  
|<span data-ttu-id="e90da-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e90da-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="e90da-169">Int16</span><span class="sxs-lookup"><span data-stu-id="e90da-169">Int16</span></span>|  
|<span data-ttu-id="e90da-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e90da-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="e90da-171">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-171">Int64</span></span>|  
|<span data-ttu-id="e90da-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="e90da-173">String</span><span class="sxs-lookup"><span data-stu-id="e90da-173">String</span></span>|  
|<span data-ttu-id="e90da-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="e90da-175">String</span><span class="sxs-lookup"><span data-stu-id="e90da-175">String</span></span>|  
|<span data-ttu-id="e90da-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="e90da-177">String</span><span class="sxs-lookup"><span data-stu-id="e90da-177">String</span></span>|  
|<span data-ttu-id="e90da-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="e90da-179">String</span><span class="sxs-lookup"><span data-stu-id="e90da-179">String</span></span>|  
|<span data-ttu-id="e90da-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="e90da-181">String</span><span class="sxs-lookup"><span data-stu-id="e90da-181">String</span></span>|  
|<span data-ttu-id="e90da-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-182">COLLATION_NAME</span></span>|<span data-ttu-id="e90da-183">String</span><span class="sxs-lookup"><span data-stu-id="e90da-183">String</span></span>|  
|<span data-ttu-id="e90da-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="e90da-185">String</span><span class="sxs-lookup"><span data-stu-id="e90da-185">String</span></span>|  
|<span data-ttu-id="e90da-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="e90da-187">String</span><span class="sxs-lookup"><span data-stu-id="e90da-187">String</span></span>|  
|<span data-ttu-id="e90da-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-188">DOMAIN_NAME</span></span>|<span data-ttu-id="e90da-189">String</span><span class="sxs-lookup"><span data-stu-id="e90da-189">String</span></span>|  
|<span data-ttu-id="e90da-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-190">DESCRIPTION</span></span>|<span data-ttu-id="e90da-191">String</span><span class="sxs-lookup"><span data-stu-id="e90da-191">String</span></span>|  
|<span data-ttu-id="e90da-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="e90da-192">COLUMN_LCID</span></span>|<span data-ttu-id="e90da-193">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-193">Int32</span></span>|  
|<span data-ttu-id="e90da-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="e90da-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="e90da-195">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-195">Int32</span></span>|  
|<span data-ttu-id="e90da-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="e90da-196">COLUMN_SORTID</span></span>|<span data-ttu-id="e90da-197">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-197">Int32</span></span>|  
|<span data-ttu-id="e90da-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="e90da-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="e90da-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="e90da-199">Byte[]</span></span>|  
|<span data-ttu-id="e90da-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="e90da-200">IS_COMPUTED</span></span>|<span data-ttu-id="e90da-201">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e90da-202">手順</span><span class="sxs-lookup"><span data-stu-id="e90da-202">Procedures</span></span>  
  
|<span data-ttu-id="e90da-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-203">ColumnName</span></span>|<span data-ttu-id="e90da-204">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e90da-206">String</span><span class="sxs-lookup"><span data-stu-id="e90da-206">String</span></span>|  
|<span data-ttu-id="e90da-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e90da-208">String</span><span class="sxs-lookup"><span data-stu-id="e90da-208">String</span></span>|  
|<span data-ttu-id="e90da-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="e90da-210">String</span><span class="sxs-lookup"><span data-stu-id="e90da-210">String</span></span>|  
|<span data-ttu-id="e90da-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e90da-212">Int16</span><span class="sxs-lookup"><span data-stu-id="e90da-212">Int16</span></span>|  
|<span data-ttu-id="e90da-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e90da-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="e90da-214">String</span><span class="sxs-lookup"><span data-stu-id="e90da-214">String</span></span>|  
|<span data-ttu-id="e90da-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-215">DESCRIPTION</span></span>|<span data-ttu-id="e90da-216">String</span><span class="sxs-lookup"><span data-stu-id="e90da-216">String</span></span>|  
|<span data-ttu-id="e90da-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e90da-217">DATE_CREATED</span></span>|<span data-ttu-id="e90da-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-218">DateTime</span></span>|  
|<span data-ttu-id="e90da-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e90da-219">DATE_MODIFIED</span></span>|<span data-ttu-id="e90da-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="e90da-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e90da-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="e90da-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-222">ColumnName</span></span>|<span data-ttu-id="e90da-223">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e90da-225">String</span><span class="sxs-lookup"><span data-stu-id="e90da-225">String</span></span>|  
|<span data-ttu-id="e90da-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e90da-227">String</span><span class="sxs-lookup"><span data-stu-id="e90da-227">String</span></span>|  
|<span data-ttu-id="e90da-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="e90da-229">String</span><span class="sxs-lookup"><span data-stu-id="e90da-229">String</span></span>|  
|<span data-ttu-id="e90da-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-230">PARAMETER_NAME</span></span>|<span data-ttu-id="e90da-231">String</span><span class="sxs-lookup"><span data-stu-id="e90da-231">String</span></span>|  
|<span data-ttu-id="e90da-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e90da-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="e90da-233">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-233">Int32</span></span>|  
|<span data-ttu-id="e90da-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="e90da-235">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-235">Int32</span></span>|  
|<span data-ttu-id="e90da-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e90da-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="e90da-237">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-237">Boolean</span></span>|  
|<span data-ttu-id="e90da-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e90da-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="e90da-239">String</span><span class="sxs-lookup"><span data-stu-id="e90da-239">String</span></span>|  
|<span data-ttu-id="e90da-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e90da-240">IS_NULLABLE</span></span>|<span data-ttu-id="e90da-241">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-241">Boolean</span></span>|  
|<span data-ttu-id="e90da-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-242">DATA_TYPE</span></span>|<span data-ttu-id="e90da-243">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-243">Int32</span></span>|  
|<span data-ttu-id="e90da-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e90da-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e90da-245">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-245">Int64</span></span>|  
|<span data-ttu-id="e90da-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e90da-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e90da-247">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-247">Int64</span></span>|  
|<span data-ttu-id="e90da-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e90da-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e90da-249">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-249">Int32</span></span>|  
|<span data-ttu-id="e90da-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e90da-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="e90da-251">Int16</span><span class="sxs-lookup"><span data-stu-id="e90da-251">Int16</span></span>|  
|<span data-ttu-id="e90da-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-252">DESCRIPTION</span></span>|<span data-ttu-id="e90da-253">String</span><span class="sxs-lookup"><span data-stu-id="e90da-253">String</span></span>|  
|<span data-ttu-id="e90da-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-254">TYPE_NAME</span></span>|<span data-ttu-id="e90da-255">String</span><span class="sxs-lookup"><span data-stu-id="e90da-255">String</span></span>|  
|<span data-ttu-id="e90da-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="e90da-257">String</span><span class="sxs-lookup"><span data-stu-id="e90da-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="e90da-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="e90da-258">Catalog</span></span>  
  
|<span data-ttu-id="e90da-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-259">ColumnName</span></span>|<span data-ttu-id="e90da-260">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-261">CATALOG_NAME</span></span>|<span data-ttu-id="e90da-262">String</span><span class="sxs-lookup"><span data-stu-id="e90da-262">String</span></span>|  
|<span data-ttu-id="e90da-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-263">DESCRIPTION</span></span>|<span data-ttu-id="e90da-264">String</span><span class="sxs-lookup"><span data-stu-id="e90da-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e90da-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="e90da-265">Indexes</span></span>  
  
|<span data-ttu-id="e90da-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-266">ColumnName</span></span>|<span data-ttu-id="e90da-267">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-268">TABLE_CATALOG</span></span>|<span data-ttu-id="e90da-269">String</span><span class="sxs-lookup"><span data-stu-id="e90da-269">String</span></span>|  
|<span data-ttu-id="e90da-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="e90da-271">String</span><span class="sxs-lookup"><span data-stu-id="e90da-271">String</span></span>|  
|<span data-ttu-id="e90da-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-272">TABLE_NAME</span></span>|<span data-ttu-id="e90da-273">String</span><span class="sxs-lookup"><span data-stu-id="e90da-273">String</span></span>|  
|<span data-ttu-id="e90da-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-274">INDEX_CATALOG</span></span>|<span data-ttu-id="e90da-275">String</span><span class="sxs-lookup"><span data-stu-id="e90da-275">String</span></span>|  
|<span data-ttu-id="e90da-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="e90da-277">String</span><span class="sxs-lookup"><span data-stu-id="e90da-277">String</span></span>|  
|<span data-ttu-id="e90da-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-278">INDEX_NAME</span></span>|<span data-ttu-id="e90da-279">String</span><span class="sxs-lookup"><span data-stu-id="e90da-279">String</span></span>|  
|<span data-ttu-id="e90da-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="e90da-280">PRIMARY_KEY</span></span>|<span data-ttu-id="e90da-281">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-281">Boolean</span></span>|  
|<span data-ttu-id="e90da-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e90da-282">UNIQUE</span></span>|<span data-ttu-id="e90da-283">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-283">Boolean</span></span>|  
|<span data-ttu-id="e90da-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="e90da-284">CLUSTERED</span></span>|<span data-ttu-id="e90da-285">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-285">Boolean</span></span>|  
|<span data-ttu-id="e90da-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-286">TYPE</span></span>|<span data-ttu-id="e90da-287">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-287">Int32</span></span>|  
|<span data-ttu-id="e90da-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="e90da-288">FILL_FACTOR</span></span>|<span data-ttu-id="e90da-289">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-289">Int32</span></span>|  
|<span data-ttu-id="e90da-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="e90da-290">INITIAL_SIZE</span></span>|<span data-ttu-id="e90da-291">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-291">Int32</span></span>|  
|<span data-ttu-id="e90da-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="e90da-292">NULLS</span></span>|<span data-ttu-id="e90da-293">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-293">Int32</span></span>|  
|<span data-ttu-id="e90da-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="e90da-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="e90da-295">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-295">Boolean</span></span>|  
|<span data-ttu-id="e90da-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="e90da-296">AUTO_UPDATE</span></span>|<span data-ttu-id="e90da-297">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-297">Boolean</span></span>|  
|<span data-ttu-id="e90da-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="e90da-298">NULL_COLLATION</span></span>|<span data-ttu-id="e90da-299">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-299">Int32</span></span>|  
|<span data-ttu-id="e90da-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e90da-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="e90da-301">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-301">Int64</span></span>|  
|<span data-ttu-id="e90da-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-302">COLUMN_NAME</span></span>|<span data-ttu-id="e90da-303">String</span><span class="sxs-lookup"><span data-stu-id="e90da-303">String</span></span>|  
|<span data-ttu-id="e90da-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-304">COLUMN_GUID</span></span>|<span data-ttu-id="e90da-305">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-305">Guid</span></span>|  
|<span data-ttu-id="e90da-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e90da-306">COLUMN_PROPID</span></span>|<span data-ttu-id="e90da-307">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-307">Int64</span></span>|  
|<span data-ttu-id="e90da-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e90da-308">COLLATION</span></span>|<span data-ttu-id="e90da-309">Int16</span><span class="sxs-lookup"><span data-stu-id="e90da-309">Int16</span></span>|  
|<span data-ttu-id="e90da-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e90da-310">CARDINALITY</span></span>|<span data-ttu-id="e90da-311">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="e90da-311">Decimal</span></span>|  
|<span data-ttu-id="e90da-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="e90da-312">PAGES</span></span>|<span data-ttu-id="e90da-313">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-313">Int32</span></span>|  
|<span data-ttu-id="e90da-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e90da-314">FILTER_CONDITION</span></span>|<span data-ttu-id="e90da-315">String</span><span class="sxs-lookup"><span data-stu-id="e90da-315">String</span></span>|  
|<span data-ttu-id="e90da-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="e90da-316">INTEGRATED</span></span>|<span data-ttu-id="e90da-317">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="e90da-318">Microsoft Oracle OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="e90da-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="e90da-319">Microsoft Oracle OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e90da-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e90da-320">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e90da-320">Tables</span></span>  
  
-   <span data-ttu-id="e90da-321">列</span><span class="sxs-lookup"><span data-stu-id="e90da-321">Columns</span></span>  
  
-   <span data-ttu-id="e90da-322">手順</span><span class="sxs-lookup"><span data-stu-id="e90da-322">Procedures</span></span>  
  
-   <span data-ttu-id="e90da-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e90da-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="e90da-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e90da-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e90da-325">Views</span><span class="sxs-lookup"><span data-stu-id="e90da-325">Views</span></span>  
  
-   <span data-ttu-id="e90da-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="e90da-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="e90da-327">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e90da-327">Tables</span></span>  
  
|<span data-ttu-id="e90da-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-328">ColumnName</span></span>|<span data-ttu-id="e90da-329">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-330">TABLE_CATALOG</span></span>|<span data-ttu-id="e90da-331">String</span><span class="sxs-lookup"><span data-stu-id="e90da-331">String</span></span>|  
|<span data-ttu-id="e90da-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="e90da-333">String</span><span class="sxs-lookup"><span data-stu-id="e90da-333">String</span></span>|  
|<span data-ttu-id="e90da-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-334">TABLE_NAME</span></span>|<span data-ttu-id="e90da-335">String</span><span class="sxs-lookup"><span data-stu-id="e90da-335">String</span></span>|  
|<span data-ttu-id="e90da-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-336">TABLE_TYPE</span></span>|<span data-ttu-id="e90da-337">String</span><span class="sxs-lookup"><span data-stu-id="e90da-337">String</span></span>|  
|<span data-ttu-id="e90da-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-338">TABLE_GUID</span></span>|<span data-ttu-id="e90da-339">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-339">Guid</span></span>|  
|<span data-ttu-id="e90da-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-340">DESCRIPTION</span></span>|<span data-ttu-id="e90da-341">String</span><span class="sxs-lookup"><span data-stu-id="e90da-341">String</span></span>|  
|<span data-ttu-id="e90da-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="e90da-342">TABLE_PROPID</span></span>|<span data-ttu-id="e90da-343">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-343">Int64</span></span>|  
|<span data-ttu-id="e90da-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e90da-344">DATE_CREATED</span></span>|<span data-ttu-id="e90da-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-345">DateTime</span></span>|  
|<span data-ttu-id="e90da-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e90da-346">DATE_MODIFIED</span></span>|<span data-ttu-id="e90da-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e90da-348">列</span><span class="sxs-lookup"><span data-stu-id="e90da-348">Columns</span></span>  
  
|<span data-ttu-id="e90da-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-349">ColumnName</span></span>|<span data-ttu-id="e90da-350">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-351">TABLE_CATALOG</span></span>|<span data-ttu-id="e90da-352">String</span><span class="sxs-lookup"><span data-stu-id="e90da-352">String</span></span>|  
|<span data-ttu-id="e90da-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="e90da-354">String</span><span class="sxs-lookup"><span data-stu-id="e90da-354">String</span></span>|  
|<span data-ttu-id="e90da-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-355">TABLE_NAME</span></span>|<span data-ttu-id="e90da-356">String</span><span class="sxs-lookup"><span data-stu-id="e90da-356">String</span></span>|  
|<span data-ttu-id="e90da-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-357">COLUMN_NAME</span></span>|<span data-ttu-id="e90da-358">String</span><span class="sxs-lookup"><span data-stu-id="e90da-358">String</span></span>|  
|<span data-ttu-id="e90da-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-359">COLUMN_GUID</span></span>|<span data-ttu-id="e90da-360">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-360">Guid</span></span>|  
|<span data-ttu-id="e90da-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e90da-361">COLUMN_PROPID</span></span>|<span data-ttu-id="e90da-362">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-362">Int64</span></span>|  
|<span data-ttu-id="e90da-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e90da-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="e90da-364">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-364">Int64</span></span>|  
|<span data-ttu-id="e90da-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e90da-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="e90da-366">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-366">Boolean</span></span>|  
|<span data-ttu-id="e90da-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e90da-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="e90da-368">String</span><span class="sxs-lookup"><span data-stu-id="e90da-368">String</span></span>|  
|<span data-ttu-id="e90da-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e90da-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="e90da-370">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-370">Int64</span></span>|  
|<span data-ttu-id="e90da-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e90da-371">IS_NULLABLE</span></span>|<span data-ttu-id="e90da-372">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-372">Boolean</span></span>|  
|<span data-ttu-id="e90da-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-373">DATA_TYPE</span></span>|<span data-ttu-id="e90da-374">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-374">Int32</span></span>|  
|<span data-ttu-id="e90da-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-375">TYPE_GUID</span></span>|<span data-ttu-id="e90da-376">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-376">Guid</span></span>|  
|<span data-ttu-id="e90da-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e90da-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e90da-378">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-378">Int64</span></span>|  
|<span data-ttu-id="e90da-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e90da-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e90da-380">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-380">Int64</span></span>|  
|<span data-ttu-id="e90da-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e90da-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e90da-382">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-382">Int32</span></span>|  
|<span data-ttu-id="e90da-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e90da-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="e90da-384">Int16</span><span class="sxs-lookup"><span data-stu-id="e90da-384">Int16</span></span>|  
|<span data-ttu-id="e90da-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e90da-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="e90da-386">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-386">Int64</span></span>|  
|<span data-ttu-id="e90da-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="e90da-388">String</span><span class="sxs-lookup"><span data-stu-id="e90da-388">String</span></span>|  
|<span data-ttu-id="e90da-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="e90da-390">String</span><span class="sxs-lookup"><span data-stu-id="e90da-390">String</span></span>|  
|<span data-ttu-id="e90da-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="e90da-392">String</span><span class="sxs-lookup"><span data-stu-id="e90da-392">String</span></span>|  
|<span data-ttu-id="e90da-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="e90da-394">String</span><span class="sxs-lookup"><span data-stu-id="e90da-394">String</span></span>|  
|<span data-ttu-id="e90da-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="e90da-396">String</span><span class="sxs-lookup"><span data-stu-id="e90da-396">String</span></span>|  
|<span data-ttu-id="e90da-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-397">COLLATION_NAME</span></span>|<span data-ttu-id="e90da-398">String</span><span class="sxs-lookup"><span data-stu-id="e90da-398">String</span></span>|  
|<span data-ttu-id="e90da-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="e90da-400">String</span><span class="sxs-lookup"><span data-stu-id="e90da-400">String</span></span>|  
|<span data-ttu-id="e90da-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="e90da-402">String</span><span class="sxs-lookup"><span data-stu-id="e90da-402">String</span></span>|  
|<span data-ttu-id="e90da-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-403">DOMAIN_NAME</span></span>|<span data-ttu-id="e90da-404">String</span><span class="sxs-lookup"><span data-stu-id="e90da-404">String</span></span>|  
|<span data-ttu-id="e90da-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-405">DESCRIPTION</span></span>|<span data-ttu-id="e90da-406">String</span><span class="sxs-lookup"><span data-stu-id="e90da-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e90da-407">手順</span><span class="sxs-lookup"><span data-stu-id="e90da-407">Procedures</span></span>  
  
|<span data-ttu-id="e90da-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-408">ColumnName</span></span>|<span data-ttu-id="e90da-409">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e90da-411">String</span><span class="sxs-lookup"><span data-stu-id="e90da-411">String</span></span>|  
|<span data-ttu-id="e90da-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e90da-413">String</span><span class="sxs-lookup"><span data-stu-id="e90da-413">String</span></span>|  
|<span data-ttu-id="e90da-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="e90da-415">String</span><span class="sxs-lookup"><span data-stu-id="e90da-415">String</span></span>|  
|<span data-ttu-id="e90da-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e90da-417">Int16</span><span class="sxs-lookup"><span data-stu-id="e90da-417">Int16</span></span>|  
|<span data-ttu-id="e90da-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e90da-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="e90da-419">String</span><span class="sxs-lookup"><span data-stu-id="e90da-419">String</span></span>|  
|<span data-ttu-id="e90da-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-420">DESCRIPTION</span></span>|<span data-ttu-id="e90da-421">String</span><span class="sxs-lookup"><span data-stu-id="e90da-421">String</span></span>|  
|<span data-ttu-id="e90da-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e90da-422">DATE_CREATED</span></span>|<span data-ttu-id="e90da-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-423">DateTime</span></span>|  
|<span data-ttu-id="e90da-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e90da-424">DATE_MODIFIED</span></span>|<span data-ttu-id="e90da-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="e90da-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e90da-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="e90da-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-427">ColumnName</span></span>|<span data-ttu-id="e90da-428">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e90da-430">String</span><span class="sxs-lookup"><span data-stu-id="e90da-430">String</span></span>|  
|<span data-ttu-id="e90da-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e90da-432">String</span><span class="sxs-lookup"><span data-stu-id="e90da-432">String</span></span>|  
|<span data-ttu-id="e90da-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="e90da-434">String</span><span class="sxs-lookup"><span data-stu-id="e90da-434">String</span></span>|  
|<span data-ttu-id="e90da-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-435">COLUMN_NAME</span></span>|<span data-ttu-id="e90da-436">String</span><span class="sxs-lookup"><span data-stu-id="e90da-436">String</span></span>|  
|<span data-ttu-id="e90da-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-437">COLUMN_GUID</span></span>|<span data-ttu-id="e90da-438">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-438">Guid</span></span>|  
|<span data-ttu-id="e90da-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e90da-439">COLUMN_PROPID</span></span>|<span data-ttu-id="e90da-440">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-440">Int64</span></span>|  
|<span data-ttu-id="e90da-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="e90da-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="e90da-442">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-442">Int64</span></span>|  
|<span data-ttu-id="e90da-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e90da-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="e90da-444">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-444">Int64</span></span>|  
|<span data-ttu-id="e90da-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e90da-445">IS_NULLABLE</span></span>|<span data-ttu-id="e90da-446">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-446">Boolean</span></span>|  
|<span data-ttu-id="e90da-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-447">DATA_TYPE</span></span>|<span data-ttu-id="e90da-448">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-448">Int32</span></span>|  
|<span data-ttu-id="e90da-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-449">TYPE_GUID</span></span>|<span data-ttu-id="e90da-450">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-450">Guid</span></span>|  
|<span data-ttu-id="e90da-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e90da-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e90da-452">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-452">Int64</span></span>|  
|<span data-ttu-id="e90da-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e90da-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e90da-454">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-454">Int64</span></span>|  
|<span data-ttu-id="e90da-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e90da-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e90da-456">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-456">Int32</span></span>|  
|<span data-ttu-id="e90da-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e90da-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="e90da-458">Int16</span><span class="sxs-lookup"><span data-stu-id="e90da-458">Int16</span></span>|  
|<span data-ttu-id="e90da-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-459">DESCRIPTION</span></span>|<span data-ttu-id="e90da-460">String</span><span class="sxs-lookup"><span data-stu-id="e90da-460">String</span></span>|  
|<span data-ttu-id="e90da-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="e90da-461">OVERLOAD</span></span>|<span data-ttu-id="e90da-462">Int16</span><span class="sxs-lookup"><span data-stu-id="e90da-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="e90da-463">Views</span><span class="sxs-lookup"><span data-stu-id="e90da-463">Views</span></span>  
  
|<span data-ttu-id="e90da-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-464">ColumnName</span></span>|<span data-ttu-id="e90da-465">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-466">TABLE_CATALOG</span></span>|<span data-ttu-id="e90da-467">String</span><span class="sxs-lookup"><span data-stu-id="e90da-467">String</span></span>|  
|<span data-ttu-id="e90da-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="e90da-469">String</span><span class="sxs-lookup"><span data-stu-id="e90da-469">String</span></span>|  
|<span data-ttu-id="e90da-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-470">TABLE_NAME</span></span>|<span data-ttu-id="e90da-471">String</span><span class="sxs-lookup"><span data-stu-id="e90da-471">String</span></span>|  
|<span data-ttu-id="e90da-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e90da-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="e90da-473">String</span><span class="sxs-lookup"><span data-stu-id="e90da-473">String</span></span>|  
|<span data-ttu-id="e90da-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-474">CHECK_OPTION</span></span>|<span data-ttu-id="e90da-475">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-475">Boolean</span></span>|  
|<span data-ttu-id="e90da-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="e90da-476">IS_UPDATABLE</span></span>|<span data-ttu-id="e90da-477">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-477">Boolean</span></span>|  
|<span data-ttu-id="e90da-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-478">DESCRIPTION</span></span>|<span data-ttu-id="e90da-479">String</span><span class="sxs-lookup"><span data-stu-id="e90da-479">String</span></span>|  
|<span data-ttu-id="e90da-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e90da-480">DATE_CREATED</span></span>|<span data-ttu-id="e90da-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-481">DateTime</span></span>|  
|<span data-ttu-id="e90da-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e90da-482">DATE_MODIFIED</span></span>|<span data-ttu-id="e90da-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e90da-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="e90da-484">Indexes</span></span>  
  
|<span data-ttu-id="e90da-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-485">ColumnName</span></span>|<span data-ttu-id="e90da-486">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-487">TABLE_CATALOG</span></span>|<span data-ttu-id="e90da-488">String</span><span class="sxs-lookup"><span data-stu-id="e90da-488">String</span></span>|  
|<span data-ttu-id="e90da-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="e90da-490">String</span><span class="sxs-lookup"><span data-stu-id="e90da-490">String</span></span>|  
|<span data-ttu-id="e90da-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-491">TABLE_NAME</span></span>|<span data-ttu-id="e90da-492">String</span><span class="sxs-lookup"><span data-stu-id="e90da-492">String</span></span>|  
|<span data-ttu-id="e90da-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-493">INDEX_CATALOG</span></span>|<span data-ttu-id="e90da-494">String</span><span class="sxs-lookup"><span data-stu-id="e90da-494">String</span></span>|  
|<span data-ttu-id="e90da-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="e90da-496">String</span><span class="sxs-lookup"><span data-stu-id="e90da-496">String</span></span>|  
|<span data-ttu-id="e90da-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-497">INDEX_NAME</span></span>|<span data-ttu-id="e90da-498">String</span><span class="sxs-lookup"><span data-stu-id="e90da-498">String</span></span>|  
|<span data-ttu-id="e90da-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="e90da-499">PRIMARY_KEY</span></span>|<span data-ttu-id="e90da-500">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-500">Boolean</span></span>|  
|<span data-ttu-id="e90da-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e90da-501">UNIQUE</span></span>|<span data-ttu-id="e90da-502">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-502">Boolean</span></span>|  
|<span data-ttu-id="e90da-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="e90da-503">CLUSTERED</span></span>|<span data-ttu-id="e90da-504">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-504">Boolean</span></span>|  
|<span data-ttu-id="e90da-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-505">TYPE</span></span>|<span data-ttu-id="e90da-506">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-506">Int32</span></span>|  
|<span data-ttu-id="e90da-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="e90da-507">FILL_FACTOR</span></span>|<span data-ttu-id="e90da-508">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-508">Int32</span></span>|  
|<span data-ttu-id="e90da-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="e90da-509">INITIAL_SIZE</span></span>|<span data-ttu-id="e90da-510">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-510">Int32</span></span>|  
|<span data-ttu-id="e90da-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="e90da-511">NULLS</span></span>|<span data-ttu-id="e90da-512">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-512">Int32</span></span>|  
|<span data-ttu-id="e90da-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="e90da-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="e90da-514">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-514">Boolean</span></span>|  
|<span data-ttu-id="e90da-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="e90da-515">AUTO_UPDATE</span></span>|<span data-ttu-id="e90da-516">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-516">Boolean</span></span>|  
|<span data-ttu-id="e90da-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="e90da-517">NULL_COLLATION</span></span>|<span data-ttu-id="e90da-518">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-518">Int32</span></span>|  
|<span data-ttu-id="e90da-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e90da-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="e90da-520">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-520">Int64</span></span>|  
|<span data-ttu-id="e90da-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-521">COLUMN_NAME</span></span>|<span data-ttu-id="e90da-522">String</span><span class="sxs-lookup"><span data-stu-id="e90da-522">String</span></span>|  
|<span data-ttu-id="e90da-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-523">COLUMN_GUID</span></span>|<span data-ttu-id="e90da-524">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-524">Guid</span></span>|  
|<span data-ttu-id="e90da-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e90da-525">COLUMN_PROPID</span></span>|<span data-ttu-id="e90da-526">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-526">Int64</span></span>|  
|<span data-ttu-id="e90da-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e90da-527">COLLATION</span></span>|<span data-ttu-id="e90da-528">Int16</span><span class="sxs-lookup"><span data-stu-id="e90da-528">Int16</span></span>|  
|<span data-ttu-id="e90da-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e90da-529">CARDINALITY</span></span>|<span data-ttu-id="e90da-530">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="e90da-530">Decimal</span></span>|  
|<span data-ttu-id="e90da-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="e90da-531">PAGES</span></span>|<span data-ttu-id="e90da-532">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-532">Int32</span></span>|  
|<span data-ttu-id="e90da-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e90da-533">FILTER_CONDITION</span></span>|<span data-ttu-id="e90da-534">String</span><span class="sxs-lookup"><span data-stu-id="e90da-534">String</span></span>|  
|<span data-ttu-id="e90da-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="e90da-535">INTEGRATED</span></span>|<span data-ttu-id="e90da-536">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="e90da-537">Microsoft Jet OLE DB Provider</span><span class="sxs-lookup"><span data-stu-id="e90da-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="e90da-538">Microsoft Jet OLE DB Driver は、共通のスキーマ コレクションに加えて次のスキーマ コレクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e90da-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e90da-539">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e90da-539">Tables</span></span>  
  
-   <span data-ttu-id="e90da-540">列</span><span class="sxs-lookup"><span data-stu-id="e90da-540">Columns</span></span>  
  
-   <span data-ttu-id="e90da-541">手順</span><span class="sxs-lookup"><span data-stu-id="e90da-541">Procedures</span></span>  
  
-   <span data-ttu-id="e90da-542">Views</span><span class="sxs-lookup"><span data-stu-id="e90da-542">Views</span></span>  
  
-   <span data-ttu-id="e90da-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="e90da-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="e90da-544">[テーブル]</span><span class="sxs-lookup"><span data-stu-id="e90da-544">Tables</span></span>  
  
|<span data-ttu-id="e90da-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-545">ColumnName</span></span>|<span data-ttu-id="e90da-546">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-547">TABLE_CATALOG</span></span>|<span data-ttu-id="e90da-548">String</span><span class="sxs-lookup"><span data-stu-id="e90da-548">String</span></span>|  
|<span data-ttu-id="e90da-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="e90da-550">String</span><span class="sxs-lookup"><span data-stu-id="e90da-550">String</span></span>|  
|<span data-ttu-id="e90da-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-551">TABLE_NAME</span></span>|<span data-ttu-id="e90da-552">String</span><span class="sxs-lookup"><span data-stu-id="e90da-552">String</span></span>|  
|<span data-ttu-id="e90da-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-553">TABLE_TYPE</span></span>|<span data-ttu-id="e90da-554">String</span><span class="sxs-lookup"><span data-stu-id="e90da-554">String</span></span>|  
|<span data-ttu-id="e90da-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-555">TABLE_GUID</span></span>|<span data-ttu-id="e90da-556">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-556">Guid</span></span>|  
|<span data-ttu-id="e90da-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-557">DESCRIPTION</span></span>|<span data-ttu-id="e90da-558">String</span><span class="sxs-lookup"><span data-stu-id="e90da-558">String</span></span>|  
|<span data-ttu-id="e90da-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="e90da-559">TABLE_PROPID</span></span>|<span data-ttu-id="e90da-560">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-560">Int64</span></span>|  
|<span data-ttu-id="e90da-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e90da-561">DATE_CREATED</span></span>|<span data-ttu-id="e90da-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-562">DateTime</span></span>|  
|<span data-ttu-id="e90da-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e90da-563">DATE_MODIFIED</span></span>|<span data-ttu-id="e90da-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e90da-565">列</span><span class="sxs-lookup"><span data-stu-id="e90da-565">Columns</span></span>  
  
|<span data-ttu-id="e90da-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-566">ColumnName</span></span>|<span data-ttu-id="e90da-567">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-568">TABLE_CATALOG</span></span>|<span data-ttu-id="e90da-569">String</span><span class="sxs-lookup"><span data-stu-id="e90da-569">String</span></span>|  
|<span data-ttu-id="e90da-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="e90da-571">String</span><span class="sxs-lookup"><span data-stu-id="e90da-571">String</span></span>|  
|<span data-ttu-id="e90da-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-572">TABLE_NAME</span></span>|<span data-ttu-id="e90da-573">String</span><span class="sxs-lookup"><span data-stu-id="e90da-573">String</span></span>|  
|<span data-ttu-id="e90da-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-574">COLUMN_NAME</span></span>|<span data-ttu-id="e90da-575">String</span><span class="sxs-lookup"><span data-stu-id="e90da-575">String</span></span>|  
|<span data-ttu-id="e90da-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-576">COLUMN_GUID</span></span>|<span data-ttu-id="e90da-577">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-577">Guid</span></span>|  
|<span data-ttu-id="e90da-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e90da-578">COLUMN_PROPID</span></span>|<span data-ttu-id="e90da-579">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-579">Int64</span></span>|  
|<span data-ttu-id="e90da-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e90da-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="e90da-581">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-581">Int64</span></span>|  
|<span data-ttu-id="e90da-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e90da-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="e90da-583">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-583">Boolean</span></span>|  
|<span data-ttu-id="e90da-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e90da-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="e90da-585">String</span><span class="sxs-lookup"><span data-stu-id="e90da-585">String</span></span>|  
|<span data-ttu-id="e90da-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e90da-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="e90da-587">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-587">Int64</span></span>|  
|<span data-ttu-id="e90da-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e90da-588">IS_NULLABLE</span></span>|<span data-ttu-id="e90da-589">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-589">Boolean</span></span>|  
|<span data-ttu-id="e90da-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-590">DATA_TYPE</span></span>|<span data-ttu-id="e90da-591">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-591">Int32</span></span>|  
|<span data-ttu-id="e90da-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-592">TYPE_GUID</span></span>|<span data-ttu-id="e90da-593">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-593">Guid</span></span>|  
|<span data-ttu-id="e90da-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e90da-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e90da-595">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-595">Int64</span></span>|  
|<span data-ttu-id="e90da-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e90da-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e90da-597">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-597">Int64</span></span>|  
|<span data-ttu-id="e90da-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e90da-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e90da-599">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-599">Int32</span></span>|  
|<span data-ttu-id="e90da-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e90da-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="e90da-601">Int16</span><span class="sxs-lookup"><span data-stu-id="e90da-601">Int16</span></span>|  
|<span data-ttu-id="e90da-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e90da-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="e90da-603">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-603">Int64</span></span>|  
|<span data-ttu-id="e90da-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="e90da-605">String</span><span class="sxs-lookup"><span data-stu-id="e90da-605">String</span></span>|  
|<span data-ttu-id="e90da-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="e90da-607">String</span><span class="sxs-lookup"><span data-stu-id="e90da-607">String</span></span>|  
|<span data-ttu-id="e90da-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="e90da-609">String</span><span class="sxs-lookup"><span data-stu-id="e90da-609">String</span></span>|  
|<span data-ttu-id="e90da-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="e90da-611">String</span><span class="sxs-lookup"><span data-stu-id="e90da-611">String</span></span>|  
|<span data-ttu-id="e90da-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="e90da-613">String</span><span class="sxs-lookup"><span data-stu-id="e90da-613">String</span></span>|  
|<span data-ttu-id="e90da-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-614">COLLATION_NAME</span></span>|<span data-ttu-id="e90da-615">String</span><span class="sxs-lookup"><span data-stu-id="e90da-615">String</span></span>|  
|<span data-ttu-id="e90da-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="e90da-617">String</span><span class="sxs-lookup"><span data-stu-id="e90da-617">String</span></span>|  
|<span data-ttu-id="e90da-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="e90da-619">String</span><span class="sxs-lookup"><span data-stu-id="e90da-619">String</span></span>|  
|<span data-ttu-id="e90da-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-620">DOMAIN_NAME</span></span>|<span data-ttu-id="e90da-621">String</span><span class="sxs-lookup"><span data-stu-id="e90da-621">String</span></span>|  
|<span data-ttu-id="e90da-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-622">DESCRIPTION</span></span>|<span data-ttu-id="e90da-623">String</span><span class="sxs-lookup"><span data-stu-id="e90da-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e90da-624">手順</span><span class="sxs-lookup"><span data-stu-id="e90da-624">Procedures</span></span>  
  
|<span data-ttu-id="e90da-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-625">ColumnName</span></span>|<span data-ttu-id="e90da-626">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e90da-628">String</span><span class="sxs-lookup"><span data-stu-id="e90da-628">String</span></span>|  
|<span data-ttu-id="e90da-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e90da-630">String</span><span class="sxs-lookup"><span data-stu-id="e90da-630">String</span></span>|  
|<span data-ttu-id="e90da-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="e90da-632">String</span><span class="sxs-lookup"><span data-stu-id="e90da-632">String</span></span>|  
|<span data-ttu-id="e90da-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e90da-634">Int16</span><span class="sxs-lookup"><span data-stu-id="e90da-634">Int16</span></span>|  
|<span data-ttu-id="e90da-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e90da-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="e90da-636">String</span><span class="sxs-lookup"><span data-stu-id="e90da-636">String</span></span>|  
|<span data-ttu-id="e90da-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-637">DESCRIPTION</span></span>|<span data-ttu-id="e90da-638">String</span><span class="sxs-lookup"><span data-stu-id="e90da-638">String</span></span>|  
|<span data-ttu-id="e90da-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e90da-639">DATE_CREATED</span></span>|<span data-ttu-id="e90da-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-640">DateTime</span></span>|  
|<span data-ttu-id="e90da-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e90da-641">DATE_MODIFIED</span></span>|<span data-ttu-id="e90da-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="e90da-643">Views</span><span class="sxs-lookup"><span data-stu-id="e90da-643">Views</span></span>  
  
|<span data-ttu-id="e90da-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-644">ColumnName</span></span>|<span data-ttu-id="e90da-645">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-646">TABLE_CATALOG</span></span>|<span data-ttu-id="e90da-647">String</span><span class="sxs-lookup"><span data-stu-id="e90da-647">String</span></span>|  
|<span data-ttu-id="e90da-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="e90da-649">String</span><span class="sxs-lookup"><span data-stu-id="e90da-649">String</span></span>|  
|<span data-ttu-id="e90da-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-650">TABLE_NAME</span></span>|<span data-ttu-id="e90da-651">String</span><span class="sxs-lookup"><span data-stu-id="e90da-651">String</span></span>|  
|<span data-ttu-id="e90da-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e90da-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="e90da-653">String</span><span class="sxs-lookup"><span data-stu-id="e90da-653">String</span></span>|  
|<span data-ttu-id="e90da-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-654">CHECK_OPTION</span></span>|<span data-ttu-id="e90da-655">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-655">Boolean</span></span>|  
|<span data-ttu-id="e90da-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="e90da-656">IS_UPDATABLE</span></span>|<span data-ttu-id="e90da-657">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-657">Boolean</span></span>|  
|<span data-ttu-id="e90da-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e90da-658">DESCRIPTION</span></span>|<span data-ttu-id="e90da-659">String</span><span class="sxs-lookup"><span data-stu-id="e90da-659">String</span></span>|  
|<span data-ttu-id="e90da-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e90da-660">DATE_CREATED</span></span>|<span data-ttu-id="e90da-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-661">DateTime</span></span>|  
|<span data-ttu-id="e90da-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e90da-662">DATE_MODIFIED</span></span>|<span data-ttu-id="e90da-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="e90da-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e90da-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="e90da-664">Indexes</span></span>  
  
|<span data-ttu-id="e90da-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="e90da-665">ColumnName</span></span>|<span data-ttu-id="e90da-666">DataType</span><span class="sxs-lookup"><span data-stu-id="e90da-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e90da-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-667">TABLE_CATALOG</span></span>|<span data-ttu-id="e90da-668">String</span><span class="sxs-lookup"><span data-stu-id="e90da-668">String</span></span>|  
|<span data-ttu-id="e90da-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="e90da-670">String</span><span class="sxs-lookup"><span data-stu-id="e90da-670">String</span></span>|  
|<span data-ttu-id="e90da-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-671">TABLE_NAME</span></span>|<span data-ttu-id="e90da-672">String</span><span class="sxs-lookup"><span data-stu-id="e90da-672">String</span></span>|  
|<span data-ttu-id="e90da-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e90da-673">INDEX_CATALOG</span></span>|<span data-ttu-id="e90da-674">String</span><span class="sxs-lookup"><span data-stu-id="e90da-674">String</span></span>|  
|<span data-ttu-id="e90da-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e90da-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="e90da-676">String</span><span class="sxs-lookup"><span data-stu-id="e90da-676">String</span></span>|  
|<span data-ttu-id="e90da-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-677">INDEX_NAME</span></span>|<span data-ttu-id="e90da-678">String</span><span class="sxs-lookup"><span data-stu-id="e90da-678">String</span></span>|  
|<span data-ttu-id="e90da-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="e90da-679">PRIMARY_KEY</span></span>|<span data-ttu-id="e90da-680">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-680">Boolean</span></span>|  
|<span data-ttu-id="e90da-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e90da-681">UNIQUE</span></span>|<span data-ttu-id="e90da-682">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-682">Boolean</span></span>|  
|<span data-ttu-id="e90da-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="e90da-683">CLUSTERED</span></span>|<span data-ttu-id="e90da-684">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-684">Boolean</span></span>|  
|<span data-ttu-id="e90da-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="e90da-685">TYPE</span></span>|<span data-ttu-id="e90da-686">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-686">Int32</span></span>|  
|<span data-ttu-id="e90da-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="e90da-687">FILL_FACTOR</span></span>|<span data-ttu-id="e90da-688">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-688">Int32</span></span>|  
|<span data-ttu-id="e90da-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="e90da-689">INITIAL_SIZE</span></span>|<span data-ttu-id="e90da-690">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-690">Int32</span></span>|  
|<span data-ttu-id="e90da-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="e90da-691">NULLS</span></span>|<span data-ttu-id="e90da-692">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-692">Int32</span></span>|  
|<span data-ttu-id="e90da-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="e90da-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="e90da-694">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-694">Boolean</span></span>|  
|<span data-ttu-id="e90da-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="e90da-695">AUTO_UPDATE</span></span>|<span data-ttu-id="e90da-696">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-696">Boolean</span></span>|  
|<span data-ttu-id="e90da-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="e90da-697">NULL_COLLATION</span></span>|<span data-ttu-id="e90da-698">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-698">Int32</span></span>|  
|<span data-ttu-id="e90da-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e90da-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="e90da-700">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-700">Int64</span></span>|  
|<span data-ttu-id="e90da-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e90da-701">COLUMN_NAME</span></span>|<span data-ttu-id="e90da-702">String</span><span class="sxs-lookup"><span data-stu-id="e90da-702">String</span></span>|  
|<span data-ttu-id="e90da-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e90da-703">COLUMN_GUID</span></span>|<span data-ttu-id="e90da-704">Guid</span><span class="sxs-lookup"><span data-stu-id="e90da-704">Guid</span></span>|  
|<span data-ttu-id="e90da-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e90da-705">COLUMN_PROPID</span></span>|<span data-ttu-id="e90da-706">Int64</span><span class="sxs-lookup"><span data-stu-id="e90da-706">Int64</span></span>|  
|<span data-ttu-id="e90da-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e90da-707">COLLATION</span></span>|<span data-ttu-id="e90da-708">Int16</span><span class="sxs-lookup"><span data-stu-id="e90da-708">Int16</span></span>|  
|<span data-ttu-id="e90da-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e90da-709">CARDINALITY</span></span>|<span data-ttu-id="e90da-710">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="e90da-710">Decimal</span></span>|  
|<span data-ttu-id="e90da-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="e90da-711">PAGES</span></span>|<span data-ttu-id="e90da-712">Int32</span><span class="sxs-lookup"><span data-stu-id="e90da-712">Int32</span></span>|  
|<span data-ttu-id="e90da-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e90da-713">FILTER_CONDITION</span></span>|<span data-ttu-id="e90da-714">String</span><span class="sxs-lookup"><span data-stu-id="e90da-714">String</span></span>|  
|<span data-ttu-id="e90da-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="e90da-715">INTEGRATED</span></span>|<span data-ttu-id="e90da-716">ブール型</span><span class="sxs-lookup"><span data-stu-id="e90da-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e90da-717">関連項目</span><span class="sxs-lookup"><span data-stu-id="e90da-717">See also</span></span>

- [<span data-ttu-id="e90da-718">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="e90da-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
