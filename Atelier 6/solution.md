-- 6.1 SELECT scientists.Name, projects.Name, projects.Hours FROM `Scientists`;  
    INNER JOIN AssignedTo ON scientists.SSN = assignedto.Scientist
    INNER JOIN Projects ON assignedto.Project = projects.Code
    ORDER BY projects.Name ASC, scientists.Name ASC;

-- 6.2 SELECT Name FROM `Projects` WHERE Code NOT In ( SELECT Project FROM `AssignedTo` );
