#!/usr/bin/env python
# coding: utf-8

# In[1]:


#Importing the libraries

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

import warnings
warnings.filterwarnings('ignore')


# In[5]:


df = pd.read_csv("C:\\Users\\srika\\Downloads\\iris\\globalterrorismdb_0718.csv", encoding='latin1')
df.head()




# In[6]:


df.shape


# In[8]:


nul = []
for i in df.columns:
    if df[i].isna().sum()>0:
        nul.append(i)
len(nul)


# In[9]:


for i in nul:
    df.drop(i,axis=1,inplace=True)
df.shape


# In[10]:


df.info()


# In[11]:


df.describe()


# In[12]:


fig,axes=plt.subplots(1,1,figsize=(20,10))
sns.heatmap(df.corr())
plt.show()


# In[13]:


df.hist(figsize=(22,24))
plt.show()


# In[14]:


fig,axes=plt.subplots(1,2,figsize=(15,5))
df.groupby('attacktype1_txt')['suicide','success'].agg(sum).plot(kind='bar',ax=axes[0])
df.groupby('property')['suicide','success'].agg(sum).plot(kind='bar',ax=axes[1])
plt.xticks(rotation=360)
plt.show()


# In[15]:


sns.barplot(y=df['targtype1'], x=df['weaptype1'])


# In[16]:


fig,axes=plt.subplots(1,2,figsize=(15,7))
sns.countplot(df.success,ax=axes[0])
sns.countplot(df.vicinity,ax=axes[1])
plt.show()


# In[17]:


fig, axes = plt.subplots(1, 1, figsize=(15, 7))
sns.countplot(x=df['iyear'], hue=df['success'], ax=axes)
plt.xticks(rotation=90)
plt.title('Year VS Success')
plt.show()


# In[18]:


sns.barplot(x=df['gname'].value_counts()[1:15].index, y=df['gname'].value_counts()[1:15].values, palette='inferno')
fig = plt.gcf()
fig.set_size_inches(10, 8)
plt.title('Terrorist Organization with Highest Terror Attacks')
plt.show()


# In[19]:


plt.figure(figsize=(15,10))
sns.barplot(x=df['country_txt'].value_counts()[:15].index,y=df['country_txt'].value_counts()[:15].values)
plt.xticks(rotation=90)
plt.title('Top Countries Got Attacked')
plt.xlabel('Countries')
plt.ylabel('No. of Attacks')
plt.show()


# In[20]:


plt.figure(figsize=(15,12))
plt.xticks(rotation=360)
sns.barplot(x=df['region_txt'].value_counts().values,y=df['region_txt'].value_counts().index)
plt.title(' Top Regions affected by terrorism')
plt.show()


# In[21]:


plt.figure(figsize=(15,12))
sns.barplot(x=df['region'].value_counts()[:20].values,y=df['region'].value_counts()[:20].index)
plt.xticks(rotation=360)
plt.title('Cities Attacked by Terrorists')
plt.show()


# In[22]:


plt.subplots(1,1,figsize=(20,10))
sns.countplot(x=df.iyear,palette='tab10')
plt.xticks(rotation=90)
plt.title('Terror Attacks from 1970 to 2017')
plt.show()


# In[23]:


plt.figure(figsize=(10,10))
sns.countplot(x=df['attacktype1_txt'],order=df['attacktype1_txt'].value_counts().index,palette='rainbow')
plt.xticks(rotation=90)
plt.xlabel('Attack Type')
plt.title('Type of Attack used by Terrorists')
plt.ylabel('Number of Attacks')
plt.show()


# In[24]:


plt.figure(figsize=(20,10))
sns.countplot(x=df['targtype1_txt'],order=df['targtype1_txt'].value_counts().index,palette='flare')
plt.xticks(rotation=90)
plt.xlabel('Targets')
plt.ylabel('Number of targets')
plt.show()

